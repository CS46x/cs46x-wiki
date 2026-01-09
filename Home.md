**Owner:** TBD  
**Last updated:** 2026-01-09  
**Status:** Current

# Start Here
This wiki is the **single source of truth** for the project. Keep this Home page current; everything else hangs off it.
## How to use this wiki
- Update **Owner** and **Last updated** on every page when you make meaningful changes.
- Link to external systems of record (boards, dashboards, requirement/design docs) instead of duplicating them.
- Prefer short, frequent decision notes (see Decision Log / ADRs) to avoid re-litigating old debates.

## Required pages
- [Project Overview & Goals](Project Overview & Goals)
  - A one-page summary of the problem, who benefits, and what “success” looks like (a short demo checklist works well). This anchors the team and gives graders a clear lens for evaluation.
- [Team Standards for Development](Team Standards for Development)
  - A concise summary of the most important working rules for your team, especially as they apply to development. Should cover:
Team Communication Standards – Concise summary of 461 policy. Update if necessary.
Coding Standards – language/style guides, linting, formatting, comments, etc.
Testing Plan & How to Run Tests – What you test (unit, integration, manual checks), test data, and how to run everything.
Branching & Release – git flow, versioning, tagging, release checklist.
Coding Review – when and how is code reviewed, using pull-requests, formal review sessions, pair-programming, etc.
CI/CD – policy and pipeline overview, who builds what and when, what runs where.
- [Requirements & Scope](Requirements & Scope)
  - Your key project requirements in condensed form. Include any important user stories, features or detailed specifications, metrics (e.g., responsiveness, reliability, projected number of users), project risks, plus links to important resources (Requirements Doc). Keeps the project feasible and ties testing back to intent.
- [System Design (with diagrams)](System Design (with diagrams))
  - The big picture: main parts, how they talk, data flow, key assumptions, and links to important resources (Design Doc). Builds a shared mental model so teammates and reviewers can follow your design.
- [Developer Setup & Project Conventions](Developer Setup & Project Conventions)
  - Step-by-step: how to get the code, set it up, run it, and where things live in the repo. Reduces setup time for new contributors and TAs and avoids “works on my machine.”
- [Decision Log (short design notes)](Decision Log (short design notes))
  - Small entries with: the question, options, the choice, and why (date + owner). Prevents re-hashing old debates and shows your reasoning to graders.
- [Release Plan & Notes (milestones/demos)](Release Plan & Notes (milestones - demos))
  - For each milestone: what’s new, how to try it, and known issues. Helps you plan demos, communicate change, and track progress over the term.
- [Handoff, Reflection, and Future Work](Handoff, Reflection, and Future Work)
  - Limits of the current build, “if we had two more weeks,” and tips for the next team. Shows thoughtful reflection and sets up continuity.

## Recommended pages (listed verbatim)
The list below is verbatim from the Exploration. Use **3 or more**.

```text
Recommended pages (choose 3 or more)
Your Choice – whatever makes sense for your project.
Assumptions, Dependencies, Constraints
Risk Register & Mitigations
Data, Security, and Ethics – What data you collect, how you protect it, and any ethical risks or mitigations.
Architecture Decision Records (ADRs) – short, dated decisions with context.
API Spec – endpoints/contracts, example requests/responses.
Data Model & Schemas – ERD, migrations strategy, seed data.
UI/UX – wireframes, component library, accessibility checklist.
Observability – logging, metrics, tracing; what to check first when things break.
Security & Privacy – threat model, secrets handling, authZ/authN, data retention.
Meeting Notes & Decisions Log – quick summaries and action items.
Demo Scripts – step-by-step flows for sprint demos & final presentation.
Deployment Guide – prod/staging setup, environment variables, provisioning steps.
User Guide – user guide and walkthrough.
How it Works – Details on the ideas behind the code.
Ethics, Accessibility, & Inclusive Design – risks, mitigations, checklists.
GenAI Usage Log & Citations – how AI was used, prompts/summaries, attributions (matches course policy).
Handoff & Future Work – known gaps, next steps, wishlist, lessons learned.
Licenses & Credits – third-party deps, licenses, attributions.
Glossary – project-specific terms and abbreviations.
Release Notes / Changelog – human-readable highlights per release.
FAQ – The beginnings of a knowledge base.
```

## Recommended pages (links to included starter stubs)
These pages are included as starter stubs so teams can adopt what they need.

- [Your Choice – whatever makes sense for your project.](Your Choice – whatever makes sense for your project.)
- [Assumptions, Dependencies, Constraints](Assumptions, Dependencies, Constraints)
- [Risk Register & Mitigations](Risk Register & Mitigations)
- [Data, Security, and Ethics](Data, Security, and Ethics)
- [Architecture Decision Records (ADRs)](Architecture Decision Records (ADRs))
- [API Spec](API Spec)
- [Data Model & Schemas](Data Model & Schemas)
- [UI/UX](UI - UX)
- [Observability](Observability)
- [Security & Privacy](Security & Privacy)
- [Meeting Notes & Decisions Log](Meeting Notes & Decisions Log)
- [Demo Scripts](Demo Scripts)
- [Deployment Guide](Deployment Guide)
- [User Guide](User Guide)
- [How it Works](How it Works)
- [Ethics, Accessibility, & Inclusive Design](Ethics, Accessibility, & Inclusive Design)
- [GenAI Usage Log & Citations](GenAI Usage Log & Citations)
- [Handoff & Future Work](Handoff & Future Work)
- [Licenses & Credits](Licenses & Credits)
- [Glossary](Glossary)
- [Release Notes / Changelog](Release Notes - Changelog)
- [FAQ](FAQ)

## Single sources of truth (links only)
- Requirements doc: TBD
- Design doc: TBD
- Project board: TBD
- CI dashboard: TBD
- Release artifacts: TBD

## Demo checklist (definition of success)
- [ ] TBD
- [ ] TBD
- [ ] TBD
