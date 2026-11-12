# Agent Control Panel · Juno

> Module 4 · Deploy Agentic Systems and Workflows. Updated for the Level 2 semi-autonomous risk workflow.

## What Juno Is Doing

**Pillar:** Risk Flagging & Prioritization. **Agent level:** 2 — Semi-Autonomous. **Reasoning:** Planner–Executor with verification and bounded reassessment.

Juno reviews authorized RocketShip project evidence, identifies and deduplicates delivery risks before scoring, and recommends actions. The Planner chooses projects, milestones and dependencies to investigate; the Executor gathers evidence, assesses six weighted factors and drafts actions; Verification checks source references, freshness, calculations, confidence and permissions.

**Scoring:** Schedule 25%; business impact 25%; blockers/dependencies 20%; resource availability 15%; cost exposure 10%; requirements uncertainty 5%. Each factor is rated 0–5; total = sum of (rating / 5 × weight in percentage points). Do not assign a validated total if critical evidence is missing.

**Output:** Ranked risks and confidence, milestone dates/status, scoring breakdown and citations, mitigation checklist, draft stakeholder messages and decisions requiring PM approval. Current prototype uses static sample data and does not send or change external records.

## Agentic Workflow Diagram

![Juno Agentic Risk Assessment Workflow](./images/juno-agentic-workflow.png)

The diagram illustrates the **proposed** bounded agentic workflow, not a working live agent in the current Lovable prototype.

## Four Levers

**Stop Conditions** (Loop):

- Maximum **three** Planner–Executor–Verification cycles per assessment, enforced by application logic, not just prompt text.
- Stop immediately when verification passes; stop early if two consecutive cycles yield no meaningful progress.
- Do not repeat unchanged evidence without a specific correction to test.
- Stop immediately for unauthorized access, prohibited actions or permission failures.
- If unresolved at the limit, pause, mark **NEEDS HUMAN REVIEW**, explain the conflicting/missing evidence and ask the PM a specific question.
- Resume after PM clarification; retain assessment history and the cycle count. A fresh three-cycle budget requires a newly PM-authorized assessment, not an automatic reset.

**Structured Tool Outputs** (Tools):

- Evidence: `source_system`, `record_id`, `source_date` (or `Date Not Provided`), `source_excerpt`, `retrieved_at` when available.
- Risk: `risk_id`, `project`, `signal`, `classification`, `milestone`, `target_date`, six `factor_ratings`, `factor_evidence`, `score_or_null`, `confidence`, `missing_information`.
- Proposed action: `action_type`, `draft_payload`, `target_system`, `recipient_or_record`, `approval_status`, `execution_status`.
- Validate schemas, IDs, factor ranges and arithmetic. Never invent missing values. These are proposed data contracts for the prototype, not claims of live integrations.

**Confidence Thresholds** (Verification):

- **High:** Direct, consistent, sufficiently current evidence.
- **Medium:** Reasonable evidence with some limitations.
- **Low:** Indirect, stale, incomplete or contradictory evidence; flag uncertainty and request review.
- Publish a validated score only when all six factors are adequately supported, weights total 100%, and calculations and citations pass checks.
- Missing data is **unknown**, not zero; if critical information is absent, show **NEEDS CLARIFICATION** and no validated overall score.
- Confidence measures evidence quality, not severity. An urgent concern may be shown provisionally to the PM without a fabricated score.

**North Star** (Context):

Help the PM identify the most consequential risk, understand why it matters and choose the next responsible action quickly, while retaining evidence traceability and human control. Prototype usability goal: highest-priority risk, rationale and next action discoverable within 60 seconds.

Preserve RocketShip's documented P0–P3 priorities and distinguish committed milestones from proposed work. The source-based prototype relies on five approved historical RocketShip documents; future Jira/Slack/Confluence/Teams/OneDrive access is planned, not currently enabled.

## Rules of Engagement

**Agency Permission:**

- **Automatic:** Read authorized sources, identify risks, calculate supported scores, draft checklists and notifications, and present findings.
- **Human confirmation (future permitted writes):** Create/update a Jira item, assign work or change project records after review of the exact action and destination. **Sending remains blocked in the current prototype**; future approval-enabled sending requires an explicit policy revision and action-specific authorization.
- **Human-only decisions:** Release, budget, contracts, resource commitments, legal/regulatory determinations and strategic priority changes.
- Proposed future UI actions: **Approve & Send** (only after a revised send policy), **Approve & Apply** (only for authorized writes), or **Request Changes**. These are conceptual or simulated controls, not proof that the current Lovable dashboard implements them; no real sends or writes occur.
- After a permitted production action, verify tool success, record the outcome and report failures; approval alone is not evidence of execution.

**Access Control:**

- Use least-privilege, explicitly authorized RocketShip data and respect project/user access boundaries.
- Never use the internet or unauthorized systems to fill gaps; protect confidential information and PII.
- Separate read/draft from send/write permissions; verify approver authority for each destination.
- Never invent customer names, record IDs, dates, financial figures, staff assignments or recipients.
- Log actor, source, approval, action, destination and outcome when persistent infrastructure exists; current static prototype has no production audit backend.

**Fallback Protocols:**

- **Conflicting or outdated sources:** Show both sources and dates; mark **NEEDS CLARIFICATION** and ask for authoritative status.
- **Missing information:** Return partial findings and missing factors; withhold unsupported numeric scores.
- **Failed verification:** Recheck only when available authorized evidence could resolve the issue, within three cycles.
- **Unresolved assessment:** Pause as **NEEDS HUMAN REVIEW** with evidence, attempts and specific PM question; execute nothing consequential.
- **After PM clarification:** Resume paused work, revalidate affected factors, recalculate, show previous and revised scores and explain the change. Approval for an action is still separate.
- **Failed execution:** Report failure, retain the draft and request guidance; never endlessly retry a send or write.

**Checkpoints:**

1. **Before analysis:** Confirm authorized sources, source dates and milestone/commitment status.
2. **After identification:** Deduplicate risk signals, cite sources and classify confirmed/emerging/unclear.
3. **Before scoring:** Verify all six factor ratings, evidence, arithmetic, confidence and missing-data handling.
4. **At loop exit:** Return verified results or pause for human review, retaining attempt count and reason.
5. **After clarification:** Record PM input, reassess affected evidence, compare old/new scores and flag residual uncertainty.
6. **Before external action:** Show exact payload, destination and recipients; obtain explicit action-specific approval.
7. **After action:** Confirm actual success/failure and log outcome. Subsequent monitoring starts a separate assessment; prior approvals do not carry forward.

---

**Alignment note:** The PRD, skill file, prototype documentation and harness sketch are part of the same Juno project. The historical five-document assessment is separate from the three-project Lovable UI demonstration. The three-cycle design supersedes the older two-attempt wording; all updated documents now reflect that decision. Live monitoring, approvals and execution remain future capabilities.
