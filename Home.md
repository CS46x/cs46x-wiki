# Start Here
This wiki is the **single source of truth** for the project. Keep this Home page current; everything else hangs off it.
## Tips that keep wikis useful:
- One-page "Start Here" stays current; everything else hangs off it.
- Owners + "Last updated" at the top of each page.
- Link to single source of truth (boards, repos, dashboards) – don't duplicate anything.
- Short ADRs, often – Architecture Decision Records (ADRs) tiny notes that capture an important technical decision, the context, and the consequences. 5–10 minutes each saves hours later.
- Links to demo scripts – double as acceptance tests and presentation prep.

## REQUIRED: Must-have wiki pages (if applicable to your project)
- [Project Overview & Goals](<Project Overview & Goals.md>)
  - A one-page summary of the problem, who benefits, and what “success” looks like (a short demo checklist works well). This anchors the team and gives graders a clear lens for evaluation.
- [Team Standards for Development](<Team Standards for Development.md>)
  - A concise summary of the most important working rules for your team, especially as they apply to development. Should cover:
    - Team Communication Standards – Concise summary of 461 policy. Update if necessary.
    - Coding Standards – language/style guides, linting, formatting, comments, etc.
    - Testing Plan & How to Run Tests – What you test (unit, integration, manual checks), test data, and how to run everything.
    - Branching & Release – git flow, versioning, tagging, release checklist.
    - Coding Review – when and how is code reviewed, using pull-requests, formal review sessions, pair-programming, etc.
    - CI/CD – policy and pipeline overview, who builds what and when, what runs where.
- [Requirements & Scope](<Requirements & Scope.md>)
  - Your key project requirements in condensed form. Include any important user stories, features or detailed specifications, metrics (e.g., responsiveness, reliability, projected number of users), project risks, plus links to important resources (Requirements Doc). Keeps the project feasible and ties testing back to intent.
- [System Design (with diagrams)](<System Design (with diagrams).md>)
  - The big picture: main parts, how they talk, data flow, key assumptions, and links to important resources (Design Doc). Builds a shared mental model so teammates and reviewers can follow your design.
- [Developer Setup & Project Conventions](<Developer Setup & Project Conventions.md>)
  - Step-by-step: how to get the code, set it up, run it, and where things live in the repo. Reduces setup time for new contributors and TAs and avoids “works on my machine.”
- [Decision Log (short design notes)](<Decision Log (short design notes).md>)
  - Small entries with: the question, options, the choice, and why (date + owner). Prevents re-hashing old debates and shows your reasoning to graders.
- [Release Plan & Notes (milestones/demos)](<Release Plan & Notes (milestones - demos).md>)
  - For each milestone: what’s new, how to try it, and known issues. Helps you plan demos, communicate change, and track progress over the term.
- [Handoff, Reflection, and Future Work](<Handoff, Reflection, and Future Work.md>)
  - Limits of the current build, “if we had two more weeks,” and tips for the next team. Shows thoughtful reflection and sets up continuity.

## Recommended pages (choose 3 or more)
- [Your Choice – whatever makes sense for your project.](<Your Choice – whatever makes sense for your project..md>)
- [Assumptions, Dependencies, Constraints](<Assumptions, Dependencies, Constraints.md>)
- [Risk Register & Mitigations](<Risk Register & Mitigations.md>)
- [Data, Security, and Ethics](<Data, Security, and Ethics.md>) – What data you collect, how you protect it, and any ethical risks or mitigations.
- [Architecture Decision Records (ADRs)](<Architecture Decision Records (ADRs).md>) – short, dated decisions with context.
- [API Spec](<API Spec.md>) – endpoints/contracts, example requests/responses.
- [Data Model & Schemas](<Data Model & Schemas.md>) – ERD, migrations strategy, seed data.
- [UI / UX](<UI - UX.md>) – wireframes, component library, accessibility checklist.
- [Observability](<Observability.md>) – logging, metrics, tracing; what to check first when things break.
- [Security & Privacy](<Security & Privacy.md>) – threat model, secrets handling, authZ/authN, data retention.
- [Meeting Notes & Decisions Log](<Meeting Notes & Decisions Log.md>) – quick summaries and action items.
- [Demo Scripts](<Demo Scripts.md>) – step-by-step flows for sprint demos & final presentation.
- [Deployment Guide](<Deployment Guide.md>) – prod/staging setup, environment variables, provisioning steps.
- [User Guide](<User Guide.md>) – user guide and walkthrough.
- [How it Works](<How it Works.md>) – Details on the ideas behind the code.
- [Ethics, Accessibility, & Inclusive Design](<Ethics, Accessibility, & Inclusive Design.md>) – risks, mitigations, checklists.
- [GenAI Usage Log & Citations](<GenAI Usage Log & Citations.md>) – how AI was used, prompts/summaries, attributions (matches course policy).
- [Handoff & Future Work](<Handoff & Future Work.md>) – known gaps, next steps, wishlist, lessons learned.
- [Licenses & Credits](<Licenses & Credits.md>) – third-party deps, licenses, attributions.
- [Glossary](<Glossary.md>) – project-specific terms and abbreviations.
- [Release Notes / Changelog](<Release Notes - Changelog.md>) – human-readable highlights per release.
- [FAQ](<FAQ.md>) – The beginnings of a knowledge base.

## Demo checklist (definition of success)
- [ ] TBD
- [ ] TBD
- [ ] TBD
