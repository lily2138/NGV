# Automotive SPICE 4.1 — Capability Level 2 Generic Practices (Official Text)

> Source: VDA QMC "Automotive SPICE PAM 4.1" (public preview), section 5.3 (pp.101-105). Verbatim/paraphrased-verbatim extract for offline reference. CL2 requires **both** PA 2.1 and PA 2.2 rated at minimum "Largely achieved (L)".

## PA 2.1 — Process Performance Management

**Scope:** measures the extent to which the performance of the process itself (not just its outcomes) is managed.

**Process attribute achievements (all 8 must be evidenced):**
1. A strategy for the performance of the process is defined based on the identified objectives.
2. The performance of the process is planned.
3. The performance of the process is monitored and adjusted to meet the planning.
4. The needs for human resources including responsibilities and authorities for performing the process are determined.
5. The needs for physical and material resources are determined.
6. The persons performing the process are prepared for executing their responsibilities.
7. The physical and material resources for performing the process are identified, made available, allocated and used.
8. The interfaces between the involved parties are managed to ensure both effective communication and the assignment of responsibilities.

### GP 2.1.1 — Identify the objectives and define a strategy for the performance of the process
- Scope of process activities (incl. performance management and work-product management) is determined.
- Corresponding results to be achieved are determined.
- Process performance objectives and associated criteria are identified.
  - Note: objectives are **not** identical to project goals nor a repeat of CL1 outcomes. Examples from the standard: SUP.8 — max ratio of CIs "in work" at a milestone before next release; SYS.2 — end of requirements writing = release date − x weeks; SWE.6 — test coverage of functional safety requirements at baseline y is 100%; SUP.10 — all incoming CRs analyzed within z days.
- Assumptions/constraints considered when identifying performance objectives.
- Approach/methodology for process performance determined (may be documented jointly across processes, e.g. a project handbook or test strategy).
- **Output work products:** 19-01 Process performance strategy; 18-58 Process performance objectives.

### GP 2.1.2 — Plan the performance of the process
- Planning established per the defined objectives, criteria, strategy.
- Process activities and work packages defined.
- Estimates for work packages identified using appropriate methods.
- Schedule and milestones defined.
- **Output work products:** 14-10 Work package; 08-56 Schedule.

### GP 2.1.3 — Determine resource needs
- Human resource amount + experience/knowledge/skill needs determined from the planning.
- Physical/material resource needs determined from the planning (equipment, labs, materials, tools, licenses...).
- Required responsibilities/authorities to perform the process and manage its work products determined (formal role descriptions not strictly required).
- **Output work products:** 17-55 Resource needs.

### GP 2.1.4 — Identify and make available resources
- Individuals performing/managing the process identified and allocated per determined needs.
- Those individuals qualified to execute their responsibilities (training/mentoring/coaching).
- Other necessary resources identified, made available, allocated, and used per determined needs.
- **Output work products:** 08-61 Resource allocation.

### GP 2.1.5 — Monitor and adjust the performance of the process
- Process performance monitored to identify deviations from planning.
- Appropriate actions taken for deviations.
- Planning adjusted as necessary.
- **Output work products:** 13-14 Progress status.

### GP 2.1.6 — Manage the interfaces between involved parties
- Individuals/groups incl. required external parties involved in the process performance determined.
- Responsibilities assigned to relevant individuals/parties.
- Communication mechanisms between involved parties determined.
- Effective communication established and maintained.
- **Output work products:** 08-62 Communication matrix; 13-52 Communication evidence.

---

## PA 2.2 — Work Product Management

**Scope:** measures the extent to which the work products produced by the process are appropriately managed.

**Process attribute achievements (all 4 must be evidenced):**
1. Requirements for the work products of the process are defined.
2. Requirements for storage and control of the work products are defined.
3. The work products are appropriately identified, stored, and controlled.
4. The work products are reviewed and adjusted as necessary to meet requirements.

### GP 2.2.1 — Define the requirements for the work products
- Requirements for content/structure of work products to be produced are defined.
- Quality criteria for the work products identified.
- Appropriate review and approval criteria defined.
  - Note: sources may be best practices/lessons learned, standards, organization/customer requirements.
  - Note: some work product types may legitimately have no review/approval requirement.
- **Output work products:** 17-05 Requirements for work products; 18-59 Review and approval criteria for work products; 18-07 Quality criteria.

### GP 2.2.2 — Define the requirements for storage and control of the work products
- Requirements for storage/control defined, including identification and distribution.
  - Sources: legal requirements, data policies, best practices, tool-related requirements.
  - Storage examples: files in a file system, tickets in a tool, wiki entries, paper documents.
  - Where a base practice requires a "status", it should be managed via a defined status model.

### GP 2.2.3 — Identify, store and control the work products
- Work products to be controlled are identified.
- Stored and controlled per the requirements.
- Change control established for work products.
- Versioning and baselining performed per the storage/control requirements.
- Work products (incl. revision status) made available through appropriate mechanisms.
- **Output work products:** 13-08 Baseline; 16-00 Repository.

### GP 2.2.4 — Review and adjust work products
- Work products reviewed against defined requirements and criteria.
- Resolution of issues arising from work product reviews is ensured.
- **Output work products:** 13-19 Review evidence.

---

## How this maps to a CL2 work-product audit

For any process in scope (e.g. SYS.2, SWE.1, SUP.8, MAN.3, ...), a CL2 work-product check is really: **"for each work product this process is supposed to produce, can GP 2.2.1–2.2.4 be evidenced?"**, backed by the project-level, cross-process evidence for GP 2.1.1–2.1.6. In practice:

| GP | What the auditor looks for as evidence |
|---|---|
| 2.2.1 | A template/standard/checklist defining structure & content of the work product; documented quality criteria; a defined review/approval procedure or criteria (e.g. review checklist, approval matrix). |
| 2.2.2 | A naming convention, storage location/repository rule, access/distribution rule, and (if the BP requires status, e.g. "approved", "in work") a defined status/lifecycle model — usually in a CM plan or project handbook. |
| 2.2.3 | The actual work product instance(s): correctly named/identified, stored in the defined repository, under change control (e.g. in a VCS/ALM tool), versioned, and — where applicable — baselined; retrievable with revision history. |
| 2.2.4 | Review records/minutes with reviewer(s), date, findings, and evidence that findings were tracked to closure (not just "reviewed" but issues resolved). |

Typical CL2 findings/gaps to flag:
- Work product exists but has **no defined template/criteria** (2.2.1 gap) — e.g. no review checklist used.
- Work product stored **ad hoc** (local drive, email attachment, no versioning) instead of a controlled repository (2.2.2/2.2.3 gap).
- **No baseline** established at the point a downstream process consumes the work product (2.2.3 gap) — common finding for requirements/architecture baselines feeding SWE.2/SWE.3 etc.
- Review **happened but findings not tracked to closure**, or no reviewer/date recorded (2.2.4 gap).
- Project-level plan/schedule/resource allocation exists but has **no explicit process performance objectives** tied to it (2.1.1 gap) — a very common CL2 finding since teams plan projects but rarely state process performance objectives separately from project goals.
- No **communication matrix / interface record** between roles (e.g. SYS ↔ SWE, SW ↔ supplier) (2.1.6 gap).

Ratings use the standard A-SPICE scale: N (Not achieved, 0-15%), P (Partially achieved, >15-50%), L (Largely achieved, >50-85%), F (Fully achieved, >85-100%). CL2 requires PA 2.1 and PA 2.2 both ≥ L, **and** PA 1.1 = F (process outcomes fully achieved), for every process in the target scope.
