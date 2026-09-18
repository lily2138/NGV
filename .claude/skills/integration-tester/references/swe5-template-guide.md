# 저장소 템플릿(TPL-SWE5-001/002/003) 사용 가이드

> 이 문서는 `WP_Templates/` 아래 실제 템플릿 파일의 구조를 캐시해 둔 스냅샷이다. **작업 시작 시 실제 템플릿 파일을 다시 확인**하라 (`architecture-designer`의 `swe2-template-guide.md` 0절과 동일한 방식: `docx`/`xlsx` 스킬 또는 Bash `unzip -p`).

## 1. 산출물 명명 규칙 (등록부 `PRC-TPL-001` 기준, 2026-09-17 스냅샷)

| Template ID | 형식 | 적용 산출물 파일명(예) | 필수 내용 |
|---|---|---|---|
| TPL-SWE5-001 | DOCX | `ENG-SWE5-001_SW 통합전략 및 통합시험 명세서.docx` | 순서, 인터페이스, 회귀, 결과 |
| TPL-SWE5-002 | XLSX | `ENG-SWE5-002_SW 통합시험 케이스.xlsx` | Test ID/Trace/Integration Item/Stimulus/Expected Result/Technique/Automation |
| TPL-SWE5-003 | XLSX | `ENG-SWE5-003_SW 통합시험 결과서.xlsx` | Test ID/Trace/Result/Actual Result/Evidence Locator/Defect ID/Disposition |

- 파일명은 `<산출물 ID>_<산출물명>.<확장자>` 형식을 따른다. xlsx는 안내용 빈 행(보통 10행) 이전을 건드리지 않고 그 이후에 실제 데이터를 추가한다.
- 저장 위치: `architecture-designer`/`detailed-designer` 산출물과 동일한 완성 산출물 폴더에 둔다. 정해지지 않았으면 사용자에게 확인한다.

## 2. TPL-SWE5-001 (SW 통합전략 및 통합시험 명세서) 목차 구조 — 반드시 이 순서/제목을 유지

```
표지 / 문서 통제 / 목차   ※ 다른 ENG-SWE 템플릿과 동일한 공통 서식

1. 목적 및 적용범위 (1.1 목적 / 1.2 적용범위 / 1.3 적용 경계)
2. 통합 원칙            — 통합 단위, 단계, 위험 우선순위, 반복 가능성, 실패 격리 원칙
3. 통합 항목과 순서      — 통합 항목 ID, 선행조건, 의존성, 순서, 담당, 계획 베이스라인
4. 환경 및 형상          — 도구, 실행환경, SW 버전, 시험 데이터, 형상 식별 방법
5. 진입 및 종료 기준     — 각 통합 단계의 시작/중단/재개/완료 판정 기준 (→ 함수·콜 커버리지 100% 조건을 종료 기준에 명시)
6. 통합시험 케이스 요약  — 시험 ID, 추적 대상, 기대결과, 자동화 여부 요약 (상세는 ENG-SWE5-002)
7. 시험 설계기법         — 경계값/동등분할/의사결정표/상태전이 등 기법의 선정 근거와 적용 대상
8. 실행 및 결과 기록 규칙 — 실행 식별자, 시각, 환경, 실제결과, 증거 위치, 결함 연결 방법
9. 회귀 전략             — 변경영향에 따른 회귀 범위, 자동 실행, 결과 비교 방법
10. 실패 및 편차 처리    — 시험 실패/환경 문제/계획 편차의 분류, 보고, 재시험, 승인 절차
11. 추적성와 보고        — 아키텍처 인터페이스, 시험 케이스, 실행 결과, 결함, 보고서 연결
12. 적용 한계            — 이 통합시험으로 확인하지 못하는 범위(시스템/HIL/차량/양산 환경)
13. 추적성               — 입력 설계·형상, 시험 명세, 결과, 결함 기록의 양방향 추적
14. 참고자료             — 아키텍처, 상세설계, 검증 계획, 환경 정의, 사용 도구 자료
```

각 절 "작성 안내" 문구는 실제 내용으로 교체한다.

### 사용자 요구 대응표

| 관심사 | 대응 절 |
|---|---|
| A-SPICE SWE.5 준수 | 전체 절이 BP1~BP7 구조를 따름 (`aspice-swe5-base-practices.md` 참고) |
| ISO 26262 Part 6 기반 시험 기법 | 7장 (`iso26262-integration-test-principles.md` 1~2절) |
| 함수/콜 커버리지 100% | 5장(종료 기준에 명시) + 실제 측정은 `coverage-tooling.md` |
| 아키텍처 인터페이스·통합순서 기반 테스트 | 2장·3장(→ `ENG-SWE2-001` 6장·11장을 근거로 작성), 6장 |
| 추적성 | 11장 + 13장, `requirements-analyst`의 RTM(`ENG-TRC-001`)과 연동 |

## 3. TPL-SWE5-002 (통합시험 케이스, xlsx) 컬럼

`Test ID | Trace | Integration Item | Stimulus | Expected Result | Technique | Automation`

- `Trace`: 이 시험이 검증하는 SW 요구사항 ID(`ENG-SWE1-001`) 및/또는 아키텍처 인터페이스 ID(`ENG-SWE2-001` 6장)를 기록한다.
- `Technique`: `iso26262-integration-test-principles.md` 1~2절의 방법/기법명을 기록한다 (예: "인터페이스 시험 / 경계값분석").

## 4. TPL-SWE5-003 (통합시험 결과서, xlsx) 컬럼

`Test ID | Trace | Result | Actual Result | Evidence Locator | Defect ID | Disposition`

- `Result`: Pass/Fail. `Defect ID`: Fail인 경우 `SUP.9` 결함관리 산출물의 결함 ID를 연결한다 (있다면).
- 함수/콜 커버리지 집계 결과(파일별·전체)는 이 결과서의 요약 섹션 또는 `ENG-SWE5-001` 5장/8장에 함께 기록한다 (등록부에 커버리지 전용 컬럼이 없으므로, 결과서 상단 요약이나 별도 첨부로 남긴다).
