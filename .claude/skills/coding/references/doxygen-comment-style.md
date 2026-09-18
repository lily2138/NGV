# Python 코드의 Doxygen 방식 주석 작성법

Doxygen은 Python 독스트링을 `"""!`로 시작하면 Doxygen 주석 블록으로 인식한다(일반 `"""`는 일반 독스트링으로만 처리됨). 이 프로젝트의 모든 함수/클래스/모듈 주석은 아래 형식을 따른다.

## 함수 주석 템플릿

```python
def calculateSpeed(distanceM, timeS):
    """!
    @brief 이동 거리와 시간으로 평균 속도를 계산한다.
    @param distanceM 이동 거리 [m], 0 이상
    @param timeS 소요 시간 [s], 0보다 커야 함
    @return 평균 속도 [m/s]
    @exception ValueError timeS가 0 이하이면 발생
    """
    if timeS <= 0:
        raise ValueError("timeS must be greater than 0")
    return distanceM / timeS
```

주요 태그:
- `@brief` — 한 줄 요약 (필수)
- `@param <이름> <설명>` — 파라미터별 (파라미터 수만큼 반복)
- `@return` — 반환값 설명 (반환값이 없으면 생략 가능)
- `@exception` 또는 `@throws` — 예외 조건 (해당 시)
- `@note`, `@warning` — 보충 설명이 필요할 때 선택적으로 사용

## 클래스/모듈 주석

```python
"""!
@file sensorReader.py
@brief 센서 원시값을 읽어 정규화된 값으로 변환하는 모듈.
"""

class SensorReader:
    """!
    @brief 단일 센서 채널의 값을 읽고 보정한다.
    """
```

## 상세설계 문서와의 연결

`detailed-designer` 스킬이 작성한 함수 계약(사전조건/사후조건/부작용/예외/시간제약, `unit-design-quality.md` 1절)을 그대로 `@param`/`@return`/`@exception`/`@note`(시간제약 등)로 옮겨 적는다 — 코드 주석과 상세설계서가 서로 다른 내용을 말하지 않도록, 상세설계서를 원본으로 삼아 옮긴다.

## 테스트 함수 주석 (unittest)

테스트 함수도 예외 없이 Doxygen 형식 주석을 작성한다. 일반 함수의 `@param`/`@return` 대신 `@technique`(사용한 테스트 기법)과 `@case`(positive/negative)를 사용한다 — 테스트 케이스 도출과 TDD 절차 자체는 `tdd` 스킬(`SKILL.md`, `references/swe3-test-case-derivation.md`)을 따른다.

```python
def testRaisesValueErrorWhenTimeIsZero(self):
    """!
    @brief 사전조건(시간 > 0)을 위반하는 입력에 대해 ValueError가 발생하는지 검증한다.
    @technique 경계값분석 (사전조건 경계 0)
    @case negative
    """
    with self.assertRaises(ValueError):
        calculateSpeed(100.0, 0.0)
```

## 주석 비율 지표와의 관계

`python-quality-metrics.md` 3절의 20% 비율 지표는 이 형식의 Doxygen 주석 라인 수를 기준으로 계산한다. 형식을 지키지 않은 일반 설명 주석만 늘려서 비율을 채우지 않는다 — 반드시 위 태그 형식을 사용한다.
