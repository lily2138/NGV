# 기능 요구사항의 UML 표현 및 양방향 추적성 확보 방안

> 이 저장소는 `WP_Templates/`에 실제 요구사항/추적성 템플릿을 보유하고 있다. 아래 내용은 그 템플릿에 맞춰 작성되었다 — **작업 시작 시 반드시 실제 파일을 다시 확인**하고, 이 문서와 다르면 실제 파일을 따른다 (재확인 절차는 `architecture-designer` 스킬의 `swe2-template-guide.md` 0절과 동일한 방식: `docx`/`xlsx` 스킬 또는 Bash `unzip -p <파일> word/document.xml`/`xl/worksheets/sheet1.xml` 후 태그 제거).

## 1. 기능 요구사항 → 다이어그램 매핑 (drawio 기반)

이 저장소의 다이어그램 산출물은 draw.io(mxfile) 형식을 사용한다 (`WP_Templates/Engineering/SoftwareRequirementsAnalysis/TPL-SWE1-003_Use Case 다이어그램 템플릿.drawio` 참고). PlantUML/Mermaid 등 다른 표기 도구로 임의 대체하지 않는다.

| 요구사항 성격 | 권장 다이어그램 | 근거/템플릿 |
|---|---|---|
| 시스템-외부 액터 간 상호작용/기능 범위 | Use Case Diagram | `TPL-SWE1-003` — 도형: `boundary`(시스템 경계), `actor`(액터), `element`(Use Case/요소), `edge`(관계). 작성 안내 4항목: ①시스템 경계와 대상 기능 ②주/보조 액터 ③Use Case와 관계 ④관련 요구사항 ID |
| 기능의 처리 흐름/조건 분기 | Activity Diagram | drawio로 별도 페이지에 작성, 필요 시 SWE.1 문서 4.1절(기능 요구사항)에 링크 |
| 컴포넌트 간 메시지/시간 순서 | Sequence Diagram | drawio, SWE.2 아키텍처의 7장(동적 동작)과 연계되는 경우 `architecture-designer` 스킬과 다이어그램을 공유 |
| 모드/상태에 따라 달라지는 동작 | State Machine Diagram | drawio |
| 요구사항 간 관계 자체를 시각화 | SysML 스타일 Requirement 관계 | 별도 다이어그램 대신 2절의 관계 스테레오타입을 텍스트/RTM으로 관리 (이 저장소 템플릿은 SysML Requirement Diagram 전용 템플릿을 두지 않음) |

- Use Case 명세는 다이어그램만으로 대체하지 않고 `TPL-SWE1-002_Use Case 명세서 템플릿.docx`(기본정보/사전조건·트리거/기본흐름/대안흐름/예외흐름/사후조건)로 함께 작성한다.
- 시스템 레벨(SYS.1~SYS.5) 요구사항에 대한 전용 템플릿이 `WP_Templates`에 없다면, SWE 템플릿의 구조를 준용하되 임의로 새 구조를 만들지 말고 사용자에게 확인한다.

## 2. SysML 개념상의 추적 관계 (RTM 컬럼 구조의 근거)

아래 관계 개념은 3절의 추적성 매트릭스(RTM) 컬럼이 왜 그렇게 구성되는지 이해하는 근거로만 사용한다 — 이 저장소에서 별도의 SysML Requirement Diagram을 그리지는 않는다.

| 관계(스테레오타입) | 의미 | RTM 상의 대응 |
|---|---|---|
| «deriveReqt» | 하위 요구사항이 상위 요구사항으로부터 도출됨 | RTM의 `Upper Req` → `SW Req` 컬럼 |
| «satisfy» | 설계/구현 요소가 요구사항을 만족시킴 | RTM의 `Architecture`/`Detailed Design`/`Code` 컬럼 |
| «verify» | 테스트케이스/검증 활동이 요구사항을 검증함 | RTM의 `SWE.4`/`SWE.5`/`SWE.6` 컬럼 |

## 3. 요구사항 ID 체계

```
<계층>-REQ-<일련번호>
예) SYS-REQ-0001 (시스템 요구사항), SWE-REQ-0001 (소프트웨어 요구사항),
    SAFETY-REQ-0001 (안전요구사항), UC-0001 (Use Case ID, TPL-SWE1-002 3장 목록과 일치)
```

`TPL-SWE1-001` 2.1절(식별 및 상태 규칙)에 실제 프로젝트의 ID/상태/우선순위/변경통제 규칙을 정의하고, 이후 모든 요구사항은 그 규칙을 따른다 — 이 문서의 ID 예시보다 실제 SWE.1 문서 2.1절의 정의가 우선한다.

## 4. 추적성 매트릭스(RTM) — 저장소 실제 템플릿 사용

**직접 만들지 말고 반드시 `WP_Templates/Engineering/Traceability/TPL-TRC-001_양방향 요구사항 추적 매트릭스 템플릿.xlsx`를 복사해 사용한다.**

- 산출물 명명: `ENG-TRC-001_양방향 요구사항 추적 매트릭스.xlsx` (`PRC-TPL-001` 등록부 기준, Common/SWE 적용)
- 시트 컬럼(고정, 임의 변경 금지): `Upper Req | SW Req | Architecture | Detailed Design | Code | SWE.4 | SWE.5 | SWE.6 | Coverage`
- README 규칙: 기존 시트/컬럼 구조를 유지하고, 안내용 빈 행(템플릿 10행 이전)은 그대로 두고 **10행부터 실제 데이터**를 추가한다.
- **양방향성 확보 규칙**:
  - 새 요구사항을 추가/변경할 때마다 같은 작업 안에서 RTM 행을 추가/갱신한다 (요구사항만 쓰고 RTM 갱신을 미루지 않는다).
  - `Upper Req`가 비어있는 요구사항(고아 요구사항)이나 `SWE.4~SWE.6` 컬럼이 모두 비어있는 요구사항(미검증)은 결과 보고 시 갭으로 표시한다.
  - 요구사항을 삭제하지 않고 상태를 Obsolete로 변경 + RTM에 사유를 기록한다 (이력 보존).
- **A-SPICE 연계**: 이 RTM 자체가 SUP.8(형상관리)의 통제 대상 작업제품이며, `.claude/skills/aspice-cl2-auditor`의 GP 2.2.2/2.2.3(저장·형상통제) 기준이 그대로 적용된다. `architecture-designer` 스킬이 SWE.2 산출물을 작성할 때도 같은 RTM의 `Architecture` 컬럼을 갱신한다 — 두 스킬이 동일 RTM 파일을 공유한다.
- xlsx를 직접 읽거나 갱신할 때는 `xlsx` 스킬을 사용한다 (행 단위 데이터 추가/수정 시 서식·컬럼 구조를 보존해야 하므로 임의 재작성 금지).

## 5. 일관성 점검

요구사항을 추가/수정할 때마다, 동일 계층·인접 계층의 기존 요구사항과 용어/단위/조건이 상충하지 않는지 확인한다 (예: 같은 개념에 서로 다른 용어를 쓰지 않도록 용어집을 유지). 상충이 발견되면 임의로 하나를 선택하지 말고 사용자에게 확인한다.
