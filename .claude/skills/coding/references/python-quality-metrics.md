# Python 구현 품질 지표 및 오픈소스 측정 도구 (CLAUDE.md 구현 지침 기반)

> `CLAUDE.md`의 "구현 지침"에 명시된 4가지 지표를 오픈소스 도구로 측정·강제하는 방법을 정리한다. 도구 옵션명은 버전에 따라 달라질 수 있으므로, 실제 실행 전 설치된 버전의 `--help`로 재확인한다.

## 0. 개발 환경 공통
- 언어: Python 3.14
- 테스트 프레임워크: `unittest` (표준 라이브러리) — 서드파티 테스트 프레임워크(pytest 등)로 임의 대체하지 않는다.
- 지표 측정 도구는 오픈소스만 사용한다 (CLAUDE.md 명시 사항).

## 1. 함수 라인수 ≤ 50 (순수 코드라인 기준) & 순환복잡도 ≤ 10

**권장 도구: [`lizard`](https://pypi.org/project/lizard/)** — 함수 단위로 NLOC(순수 코드 라인수, 공백·주석 제외)와 CCN(순환복잡도)을 한 번에 측정하고, 임계값 초과 시 직접 위반으로 보고한다.

```bash
pip install lizard
lizard -l python -L 50 -C 10 <대상 경로>
```
- `-L 50`: 함수당 순수 코드 라인수(NLOC) 임계값
- `-C 10`: 함수당 순환복잡도(CCN) 임계값
- 출력에서 임계값을 초과한 함수가 있으면 경고로 표시된다 — 하나라도 있으면 구현을 완료 상태로 보고하지 않는다.

대안: `radon cc -s -a <경로>` (순환복잡도), `radon raw <경로>` (LOC 계열) 조합도 가능하나, 함수당 라인수+복잡도를 한 번에 임계값 검사하려면 `lizard`가 더 직접적이다.

## 2. 중복 코드 ≤ 7라인까지 허용 (8라인 이상 중복 시 위반)

**권장 도구: `pylint`의 duplicate-code 검사기(`similarities`)**

```bash
pylint --disable=all --enable=duplicate-code --min-similarity-lines=8 <대상 경로>
```
- `min-similarity-lines=8`으로 설정하면 "8줄 이상 동일/유사한 코드"만 위반으로 보고한다 (= 7줄까지는 허용). 버전에 따라 옵션명이 `min-similarity-lines` 대신 pylintrc의 `[SIMILARITIES] min-similarity-lines` 섹션일 수 있다.
- 대안: `jscpd`(다국어 복제 탐지기, `--min-lines 8`)도 사용 가능.

## 3. 주석 비율 ≥ 20% (Doxygen 방식)

**권장 도구: `radon raw`**

```bash
radon raw -s <파일 또는 경로>
```
- 출력의 `comments`(주석 라인수)와 `sloc`(주석·공백을 제외한 순수 코드 라인수) 값으로 비율을 계산한다: `주석비율 = comments / (comments + sloc)`.
- 파일/모듈 단위로 계산해 20% 이상인지 확인하고, 미달 시 Doxygen 스타일 주석(`references/doxygen-comment-style.md` 참고)을 보강한다.
- 주석은 반드시 Doxygen 방식(`@brief`/`@param`/`@return` 태그 등)으로 작성한다 — 일반 설명문 주석만으로는 이 지표를 만족한 것으로 보지 않는다 (형식 요건도 함께 충족해야 함).

## 4. 함수명/변수명: 3글자 이상 + 낙타 표기법(camelCase)

**중요**: 이는 PEP8(표준 Python 관례인 snake_case)과 다른 이 프로젝트만의 명시적 규칙이다. 표준 Python 관례를 따르지 말고 이 규칙을 우선한다.

- 규칙: 함수명/변수명은 소문자로 시작하는 camelCase (예: `calculateSpeed`, `sensorValue`)이며 3글자 미만 이름(`i`, `n`, `x` 등)은 금지한다. 단, 관용적으로 허용되는 루프 인덱스 등도 이 프로젝트에서는 3글자 이상 이름(`idx`, `cnt` 등)을 사용한다.
- 정규식 기준: `^[a-z][a-zA-Z0-9]{2,}$` (소문자 시작, 전체 3자 이상)
- **권장 도구: `pylint`의 naming 검사기**를 프로젝트 `.pylintrc`에서 camelCase로 재설정한다:
  ```ini
  [BASIC]
  function-naming-style=camelCase
  variable-naming-style=camelCase
  argument-naming-style=camelCase
  function-rgx=^[a-z][a-zA-Z0-9]{2,}$
  variable-rgx=^[a-z][a-zA-Z0-9]{2,}$
  argument-rgx=^[a-z][a-zA-Z0-9]{2,}$
  ```
  (pylint 버전에 따라 `*-naming-style=camelCase` 프리셋 지원 여부가 다르므로, 미지원 버전이면 `*-rgx` 정규식만 사용한다.)
- 클래스명은 이 규칙의 대상이 아니다(Python 관례상 PascalCase 유지, 별도 지시가 없는 한).

## 5. 단위테스트 Branch 커버리지 100% (CLAUDE.md "단위 테스트 지침")

**권장 도구: [`coverage.py`](https://pypi.org/project/coverage/)** (오픈소스, `--branch` 옵션으로 분기 커버리지를 직접 지원한다 — `integration-tester` 스킬의 함수/콜 커버리지처럼 별도 스크립트가 필요 없다).

```bash
pip install coverage
coverage run --branch -m unittest discover -s <단위테스트 디렉터리>
coverage report -m
```
- `coverage report -m`의 `Branch` 및 `BrPart`(부분 분기) 열이 모두 커버되어야 한다 — 리포트의 `Missing` 열에 남은 분기가 있으면 100% 미달이다.
- 100% 미달 시 `tdd` 스킬의 Red-Green-Refactor 절차로 돌아가, 누락된 분기를 실행하는 테스트 케이스를 추가한다 (커버리지를 채우기 위한 무의미한 호출을 추가하지 않는다 — 항상 실제 사전조건/경계값/의사결정표 행에 근거).
- 정말 도달 불가능한 분기(방어적 코드 등)라면 임의로 100%를 주장하지 말고 사용자에게 보고한다.

## 6. 구현 완료 판정 절차

코드를 "완료"로 보고하기 전에 위 1~5번 도구를 모두 실행하고, 위반이 하나도 없는지 확인한다 (Branch 커버리지 100% 포함). 위반이 있으면:
1. 위반 목록(파일:함수, 지표, 측정값)을 사용자에게 보고하고,
2. 가능하면 즉시 리팩터링/테스트 보강(함수 분해, 중복 제거, 주석 보강, 이름 변경, 누락 분기 테스트 추가)하여 재측정하고,
3. 정당한 예외가 필요하다고 판단되면(예: 알고리즘 특성상 분해가 부적절, 코드상 도달 불가능한 분기) 임의로 기준을 무시하지 말고 사용자에게 예외 승인을 요청한다.
