_Owner: TBD | Last updated: 2026-01-09 | Status: Draft_

# Team Standards for Development

- A concise summary of the most important working rules for your team, especially as they apply to development. Should cover:
  - Team Communication Standards – Concise summary of 461 policy. Update if necessary.
  - Coding Standards – language/style guides, linting, formatting, comments, etc.
  - Testing Plan & How to Run Tests – What you test (unit, integration, manual checks), test data, and how to run everything.
  - Branching & Release – git flow, versioning, tagging, release checklist.
  - Coding Review – when and how is code reviewed, using pull-requests, formal review sessions, pair-programming, etc.
  - CI/CD – policy and pipeline overview, who builds what and when, what runs where.

## Team Communication Standards (461 policy summary)
- Primary channel: TBD
- Response expectations: TBD
- Meeting cadence: TBD
- Decision capture: [Decision Log (short design notes)](<Decision Log (short design notes)>) and/or [Architecture Decision Records (ADRs)](<Architecture Decision Records (ADRs)>)

## Coding Standards
- Languages & style guides: TBD
- Formatting: TBD
- Linting: TBD
- Commenting & documentation: TBD
- Static analysis: TBD

## Testing Plan & How to Run Tests
### What we test
- Unit tests: TBD
- Integration tests: TBD
- Manual checks / smoke tests: TBD

### Test data
- Seed data strategy: TBD
- Fixtures strategy: TBD
- Sensitive data policy: TBD

### How to run tests
```bash
# unit
TBD

# integration
TBD

# full suite
TBD
```

## Branching & Release
- Branch model (e.g., trunk-based or GitFlow): TBD
- Branch naming: TBD
- Versioning/tagging: TBD
- Release checklist:
  - [ ] Build
  - [ ] Lint/format
  - [ ] Test suite
  - [ ] Demo script updated
  - [ ] Release notes updated

## Coding Review
- PR required: TBD
- Required approvals: TBD
- Review checklist: correctness, tests, security, maintainability
- When pair-programming is used: TBD

## CI/CD
- Pipeline triggers: TBD
- Stages: build → lint → test → package → deploy (if any)
- Environments: dev/staging/prod (if any)
- Ownership: TBD

