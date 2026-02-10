_Owner: Team | Last updated: 2026-02-10 | Status: Active_

# Team Standards for Development

This document summarizes the most important working rules for our team as they apply to development, collaboration, and delivery.

---

## Team Communication Standards (CS461 policy summary)

- **Primary channel:** Discord (team server)
- **Response expectations:**  
  - Same day response for async questions  
  - Immediate response during scheduled work sessions or deadlines
- **Meeting cadence:**  
  - Weekly standups  
  - Additional ad-hoc meetings as needed during sprint deadlines
- **Decision capture:**  
  - Decisions are documented in the  
    - [Decision Log (short design notes)](<Decision Log (short design notes)>)  
    - and/or [Architecture Decision Records (ADRs)](<Architecture Decision Records (ADRs)>)

---

## Coding Standards

- **Languages & style guides:**  
  - Backend: C# (.NET / ASP.NET Core conventions)  
  - Frontend: TypeScript (Angular style guidelines)
- **Formatting:**  
  - Default formatter conventions for C# and TypeScript  
  - Consistent naming and file organization enforced through review
- **Linting:**  
  - Frontend linting via Angular tooling  
  - Backend relies on compiler warnings and code review
- **Commenting & documentation:**  
  - Public APIs, controllers, and non-trivial logic are documented with comments  
  - Complex workflows are documented in the Wiki
- **Static analysis:**  
  - Basic static analysis via compiler warnings and PR review

---

## Testing Plan & How to Run Tests

### What we test
- **Unit tests:**  
  - Core business logic and utility functions where applicable
- **Integration tests:**  
  - API endpoints and real-time hub interactions as features stabilize
- **Manual checks / smoke tests:**  
  - Primary testing approach during active development  
  - Includes authentication flows, lobby creation, joining, messaging, and ready states

### Test data
- **Seed data strategy:**  
  - Minimal seed data for local development and testing
- **Fixtures strategy:**  
  - Test users and lobbies created as needed during testing
- **Sensitive data policy:**  
  - No real user data is stored in repositories  
  - Secrets and credentials are stored in environment variables or configuration files excluded from source control

### How to run tests
```bash
# unit tests
dotnet test

# integration tests
dotnet test

# full suite
dotnet test

## Branching & Release

### Branch model
We follow a lightweight GitFlow-inspired branching strategy with a stable release branch and an integration branch.

- **main**: Stable, release-ready code only. This branch represents production-quality milestones.
- **dev**: Primary integration branch where completed features are merged and tested together.
- **feature/<short-description>**: Feature branches created from `dev` for individual tasks (e.g., `feature/account-management-ui`).
- **bugfix/<short-description>**: Bug fix branches created from `dev` for targeted fixes.

### Branch naming
- feature/<task-name>
- bugfix/<issue-name>

### Versioning / tagging
Formal version tags are created on `main` at major milestone releases as needed.

### Release checklist
- Code merged into `dev` via reviewed pull requests
- Basic functionality tested manually and/or via automated tests
- Demo scripts updated (if applicable)
- Release notes or changelog updated
- `dev` merged into `main` when stable

## Coding Review
- All non-trivial code changes require a Pull Request (PR).
- PRs are opened against the `dev` branch.
- At least one team member must review and approve a PR before merging.
- Reviews focus on:
  - Correctness and functionality
  - Code clarity and maintainability
  - Security considerations
  - Alignment with existing architecture and standards
- Review feedback is addressed before merge.
- Squash merges are preferred to keep commit history clean.
- Pair programming is used informally for complex or high-risk features when helpful.

## CI/CD
- Pipeline triggers: Pull requests and direct pushes to main branches
- Stages: build and basic verification (tests added incrementally)
- Environments: development and local testing
- Ownership: Managed collectively by the team

