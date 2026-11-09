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

## What it demonstrates

_The one flow this prototype proves._

This protoypes allows PM's to quickly 
- identify the products that are currently at risk
- assess the risk score of each product currently at risk
- identify why products are at risk
- identify next steps to reduce product risk

_____

## Debrief

- **What worked:** The products that are currently at risk are being identified, and provided a risk score. There is also a description of how the risk score is calculated, and reasons for why specific products are at risk. 
- **What broke / felt like a toy:** At first I created a dashbaord but did not tell the Lovely prompt to "create a prototype" so the there was no interactivity. However, after I used the correct verbage a demo dashboard was created with interactivity functionality. 
- **What I'd change next pass:** Currenlty I created a dashbaord; however, I think that a dashboard that is another linke one has to manage may not be a great idea. I think if I can integrate it into JIRA or Confluence it would make more sense. Thus, in my next pass I will try to do this. Another think I need to expand on is the risk score, it is rather vague and it needs more substance and direction. I will be working on this next as well.
