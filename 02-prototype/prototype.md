# Prototype · Juno

> Module 2 · Prototype. The working build that tests your idea, made with your build tool of choice.

## Prototype link

_The public share URL from your build tool. No share URL? A screenshot of the working flow is fine, the prompt is what is assessed._
**Link to prototype:** https://lovable.dev/projects/65e562a5-be64-4a7a-a324-efd042905764

**Prompt to create prototype:**
# Build Juno: Product Risk Intelligence Dashboard - Iteration 1

## Role
You are an expert application developer building a low-fidelity prototype for Juno, RocketShip's AI Associate Product Manager. Follow the attached Juno Skill File.

## Audience
Product Managers and Product Owners responsible for product delivery.

## Task
Build one interactive dashboard that helps PMs identify, score, prioritize, and understand product delivery risks.

### 1. Risk Identification
Analyze fictional Jira tickets, Slack discussions, and Confluence documentation to identify:
- Schedule delays and approaching deadlines
- Blockers and unresolved dependencies
- Resource shortages and staffing conflicts
- Budget overruns
- Unclear requirements and scope changes

For every identified risk, display its source and affected project.

### 2. Risk Scoring
After identifying risks, calculate a weighted risk score (0–100) using:

- Schedule: 25%
- Business impact: 25%
- Blockers/dependencies: 20%
- Resource availability: 15%
- Cost exposure: 10%
- Requirements uncertainty: 5%

Rate each factor from 0–5, where 5 represents the highest risk.

Formula: Risk Score = Sum of (Factor Rating ÷ 5 × Factor Weight).

Clearly explain contributing factors. Do not assign scores when critical information is missing.

### 3. Sample Projects
Use only three fictional RocketShip projects:

**Project A: Payment Integration**
- Vendor integration blocked
- Deadline approaching
- Engineering resources limited
- Expected outcome: High/Critical risk

**Project B: Customer Onboarding**
- Minor testing delays
- Some incomplete requirements
- Expected outcome: Medium risk

**Project C: Analytics Dashboard**
- Missing staffing and timeline information
- Expected outcome: NEEDS CLARIFICATION; no overall score

Create realistic fictional source records for each project, including Jira IDs, Slack messages, and Confluence references.

### 4. Dashboard Layout
Create one screen containing:
- A ranked project risk table with scores, priorities, and confidence levels
- A selectable project detail panel
- Risk factors and scoring breakdown
- Supporting evidence with source references
- Recommended mitigation actions
- Decisions requiring PM approval

### 5. Constraints
- Use static fictional data; no live integrations or external APIs.
- Do not fabricate missing evidence within the fictional scenarios.
- Clearly distinguish verified sample facts from assumptions.
- Do not interpret missing data as low risk.
- Recommendations are advisory only; no automated actions.
- No authentication, backend, notifications, or additional screens.

## Few-Shot Example

**Input:**
Jira RS-205: Payment integration blocked by vendor.
Jira RS-210: Delivery deadline in five days.
Confluence: Payment integration required for launch.

**Expected Output:**
- Identified risk: Vendor dependency threatens launch readiness.
- Priority: High
- Evidence: Jira RS-205, RS-210; Confluence Release Plan
- Recommended action: Escalate vendor dependency and confirm resolution timeline.
- Confidence: High for the existence of the blocker; delivery impact requires further assessment.
- Overall risk score: Calculate only after reviewing all six scoring factors.

## Success Criteria
A PM can identify the highest-risk project, understand why it is at risk, inspect supporting evidence, and determine the next action within 60 seconds.

Build only this initial low-fidelity prototype. Avoid unnecessary features, complex styling, and additional development.

# Juno Dashboard - Iteration 2

Update the existing dashboard. Do not rebuild it or add new pages.

1. **Project Selection:** Add a dropdown to the risk details panel allowing users to select Payment Integration, Customer Onboarding, or Analytics Dashboard. Default to the highest-risk project. Update all details dynamically when a different project is selected.

2. **Individual Risks:** Within the selected project, provide a dropdown listing all identified risks. Display the selected risk's severity, evidence, contributing factors, and recommended mitigation.

3. **Milestones:** Display the current milestone, planned completion date, days remaining or overdue, and delivery status (On Track, At Risk, Delayed, or Unknown). Use fictional dates consistent with the sample project records.

4. **Action Checklist:** Display recommended mitigation tasks with interactive checkboxes, suggested owners, and due dates where available. Show completion progress. Do not automatically change the project's risk score when a task is checked.

5. **Stakeholder Notifications:** Identify relevant stakeholders who should be informed of delays or critical blockers. Include the reason for notification and a draft message for PM review. Do not send messages or trigger external notifications.

## Constraints
- Preserve the existing dashboard layout and scoring methodology.
- Use only the three existing fictional projects.
- Keep the experience on one screen.
- Do not add live integrations, backend services, or additional pages.
- Do not invent actual employee names or contact information; use fictional roles such as Engineering Lead or Product Director.
- Ensure all dropdowns and checkboxes work.
- Keep changes minimal to conserve development credits.

## Success Criteria
A PM can select any project, inspect its individual risks, review milestone status, track mitigation actions, and identify stakeholders requiring notification—all within one dashboard.
_____

## Current Prototype Scope and Relationship to Later Modules

The Lovable dashboard is a **static, interactive UI demonstration** of Juno's third pillar, risk flagging and prioritization. It uses **three invented projects** (Payment Integration, Customer Onboarding, Analytics Dashboard) and illustrative Jira/Slack/Confluence-style records. These records are fictional demonstration data; the prototype has no live integrations, backend, automated source retrieval, actual message sending, or project-record writes.

The five historical RocketShip documents used in the later PRD and harness are a **separate, source-grounded evaluation scenario**. Do not describe the fictional dashboard records as extracted from those five documents. The first two Juno pillars—signal synthesis and specification drafting—are defined in the skill file but not implemented as prototype screens.

**Subsequent design decisions (not proof of implementation):** The Module 3 PRD formalizes the six weighted risk factors, the requirement for evidence supporting every factor before displaying a numeric score, confidence distinct from severity, and a verification/evaluation plan. Module 4 specifies a proposed Level 2 Planner–Executor–Verification controller with at most three cycles, no-progress stopping, `NEEDS HUMAN REVIEW` handoff, reassessment after PM clarification, and action-specific approvals. These behaviors should be implemented and tested in a future iteration rather than claimed as working in this build.

**Status definitions:** `NEEDS CLARIFICATION` indicates unresolved evidence; `SCORE UNAVAILABLE` means a numeric total cannot be validated; `NEEDS HUMAN REVIEW` is the proposed agentic-loop escalation state. All stakeholder messages remain drafts, and checklist completion does not change risk scores automatically.

## What it demonstrates

_The one flow this prototype proves._

This prototype allows PMs to quickly 
- identify which fictional sample projects have flagged risks
- review scores only where the sample evidence supports all six factors
- inspect why those projects are at risk
- identify proposed next steps to reduce product risk

_____

## Debrief

- **What worked:** The interactive sample dashboard identifies and explains risks across three fictional projects, presents scoring information where available, and lets PMs explore risk evidence and proposed mitigations. Its calculated values and data coverage still require formal verification against the later PRD criteria. 
- **What broke / felt like a toy:** The first Lovable prompt produced a noninteractive dashboard; after explicitly requesting a prototype, the next iteration added interactive controls. This remains a static-data demonstration, not a live agentic system. 
- **What I'd change next pass:** A standalone dashboard may add another destination for PMs to manage; an eventual Jira or Confluence embedded experience may be more useful. The risk-scoring model has since been specified in the PRD, but its six-factor evidence checks and the Module 4 agentic loop still need implementation and testing in a later prototype iteration.
