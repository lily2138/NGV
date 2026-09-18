# 함수 커버리지 · 콜 커버리지 측정 방법 (Python, 오픈소스 도구 기반)

Python 생태계의 표준 오픈소스 커버리지 도구 `coverage.py`는 문장(statement)/분기(branch) 커버리지를 측정하며, ISO 26262가 말하는 "함수 커버리지"·"콜 커버리지"를 이름 그대로 산출하지는 않는다. 따라서 `coverage.py`가 산출한 실행 라인 정보와, Python 표준 라이브러리 `ast`(추상구문트리)로 분석한 함수 정의 위치·호출 지점을 결합해 두 지표를 계산한다. 두 도구 모두 오픈소스/표준 라이브러리다.

## 0. 실행 절차 개요

1. `pip install coverage` (아직 설치되어 있지 않다면).
2. 통합시험 스위트를 커버리지 계측하에 실행한다:
   ```bash
   coverage run -m unittest discover -s <통합시험 디렉터리>
   coverage json -o coverage.json
   ```
3. 아래 스크립트로 대상 소스 파일별 함수 커버리지·콜 커버리지를 계산한다.
4. 100%에 미달하면 `iso26262-integration-test-principles.md` 3절의 절차(시험 추가 또는 도달불가 코드 보고)를 따른다.

## 1. 커버리지 계산 스크립트

아래 스크립트를 저장소에 (예: `tools/measureFunctionCallCoverage.py`) 두고 재사용한다. 신규 프로젝트 구조에 맞춰 경로만 조정한다.

```python
"""!
@file measureFunctionCallCoverage.py
@brief coverage.py의 실행 라인 정보와 ast 분석을 결합해 ISO 26262-6 스타일의
       함수 커버리지·콜 커버리지를 계산한다.
"""
import ast
import json
import sys


def loadCoveredLines(coverageJsonPath, sourcePath):
    """!
    @brief coverage.py의 JSON 리포트에서 특정 소스 파일의 실행된 라인 집합을 읽는다.
    @param coverageJsonPath `coverage json -o`로 생성한 JSON 파일 경로
    @param sourcePath 분석 대상 소스 파일 경로 (coverage.json의 키와 동일한 표기여야 함)
    @return 실행된 라인 번호의 집합(set)
    """
    with open(coverageJsonPath, encoding="utf-8") as jsonFile:
        coverageData = json.load(jsonFile)
    fileEntry = coverageData["files"].get(sourcePath)
    if fileEntry is None:
        return set()
    return set(fileEntry["executed_lines"])


def collectFunctionEntries(tree):
    """!
    @brief 소스 트리에서 모든 함수(동기/비동기)의 이름과 첫 실행 라인을 수집한다.
    @param tree ast.parse로 생성한 구문 트리
    @return (함수명, 첫 실행 라인번호) 튜플 목록
    """
    entries = []
    for node in ast.walk(tree):
        if isinstance(node, (ast.FunctionDef, ast.AsyncFunctionDef)):
            firstLine = node.body[0].lineno if node.body else node.lineno
            entries.append((node.name, firstLine))
    return entries


def collectCallSites(tree):
    """!
    @brief 소스 트리에서 모든 함수 호출 지점의 라인번호를 수집한다.
    @param tree ast.parse로 생성한 구문 트리
    @return 호출 지점 라인번호 목록 (같은 라인에 여러 호출이 있으면 중복 포함)
    """
    return [node.lineno for node in ast.walk(tree) if isinstance(node, ast.Call)]


def measureFile(sourcePath, coveredLines):
    """!
    @brief 한 소스 파일의 함수 커버리지와 콜 커버리지를 계산한다.
    @param sourcePath 분석 대상 소스 파일 경로
    @param coveredLines coverage.py가 보고한 실행된 라인 집합
    @return (함수커버리지 퍼센트, 콜커버리지 퍼센트, 미호출 함수명 목록)
    """
    with open(sourcePath, encoding="utf-8") as sourceFile:
        tree = ast.parse(sourceFile.read(), filename=sourcePath)

    functionEntries = collectFunctionEntries(tree)
    callSites = collectCallSites(tree)

    coveredFunctionCount = sum(1 for _, line in functionEntries if line in coveredLines)
    coveredCallCount = sum(1 for line in callSites if line in coveredLines)

    functionCoverage = (
        coveredFunctionCount / len(functionEntries) * 100 if functionEntries else 100.0
    )
    callCoverage = coveredCallCount / len(callSites) * 100 if callSites else 100.0

    uncoveredFunctions = [name for name, line in functionEntries if line not in coveredLines]

    return functionCoverage, callCoverage, uncoveredFunctions


def main():
    """!
    @brief 커맨드라인에서 coverage.json 경로와 소스 파일 경로를 받아 결과를 출력한다.
           함수/콜 커버리지가 100%에 미달하면 종료코드 1을 반환한다.
    """
    coverageJsonPath, sourcePath = sys.argv[1], sys.argv[2]
    coveredLines = loadCoveredLines(coverageJsonPath, sourcePath)
    functionCoverage, callCoverage, uncoveredFunctions = measureFile(sourcePath, coveredLines)

    print(f"{sourcePath}: functionCoverage={functionCoverage:.1f}% callCoverage={callCoverage:.1f}%")
    if uncoveredFunctions:
        print("  미호출 함수:", ", ".join(uncoveredFunctions))

    if functionCoverage < 100.0 or callCoverage < 100.0:
        sys.exit(1)


if __name__ == "__main__":
    main()
```

사용 예:
```bash
python tools/measureFunctionCallCoverage.py coverage.json src/sensorFusion.py
```

여러 파일을 검사해야 하면 대상 파일 목록을 순회하며 호출하고, 하나라도 100% 미달이면 통합시험을 완료로 보고하지 않는다.

## 2. 한계와 주의사항

- 이 스크립트는 "함수의 첫 실행 라인이 실행됐는가"로 함수 호출 여부를, "호출 표현식이 위치한 라인이 실행됐는가"로 호출 지점 실행 여부를 근사한다. 한 라인에 여러 함수 정의/호출이 있는 비정상적으로 압축된 코드에서는 부정확할 수 있다 — `coding` 스킬의 함수 라인수 제한(≤50라인) 및 일반적인 코딩 스타일 하에서는 문제가 되지 않는다.
- `coverage.py`의 라인 실행 정보는 `try`/`except`, 데코레이터, 컴프리헨션 등에서 라인 매핑이 도구 버전에 따라 달라질 수 있다. 결과가 직관과 다르면 `coverage html`로 시각적 리포트를 함께 확인한다.
- 이 계산은 Python 소스 코드 자체의 정적 구조(ast)와 동적 실행 기록(coverage.py)을 결합한 것이며, ISO 26262-6 Table 12의 "함수 커버리지"·"콜 커버리지" 정의(대상 언어가 C/C++인 경우가 많음)를 Python에 맞게 재현한 것이다 — 공식 인증 심사에서 상용 임베디드 커버리지 툴 결과를 요구하는 경우, 이 스크립트 결과만으로 대체 가능한지 사용자와 확인한다.
