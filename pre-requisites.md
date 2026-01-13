# Prerequisites for Successful AI-Assisted Development

This document helps teams evaluate their readiness for working effectively with AI coding agents. While these are generally good engineering practices, they become critical when working with AI assistants - the absence of any item directly limits what an AI agent can accomplish autonomously.

---

## Evaluation Checklist

Use this checklist to assess your team's readiness:

| # | Area | Item | Status |
|---|------|------|--------|
| 1 | Code as Source of Truth | System fully expressed in source code | ⬜ |
| 2 | | Fully automated, deterministic build | ⬜ |
| 3 | Testing | Isolated, self-contained databases | ⬜ |
| 4 | | Comprehensive, fast unit tests | ⬜ |
| 5 | | End-to-end tests | ⬜ |
| 6 | Code Quality | Clear project structure and conventions | ⬜ |
| 7 | | Automated linting and formatting | ⬜ |
| 8 | Environment | Environment parity (dev ≈ prod) | ⬜ |
| 9 | | Actionable error messages and logs | ⬜ |
| 10 | Documentation | Accessible, current documentation | ⬜ |

---

## Core Principle: Everything as Code

### 1. System Fully Expressed in Source Code

**What this means:** Every artifact that defines your system - database schemas, infrastructure, configuration, environment setup, deployment processes - exists as version-controlled source code.

**Why it matters for AI agents:** An AI agent can only work with what it can read and modify. If your database schema exists only as the current state of a production database, or your infrastructure exists only as manually-configured cloud resources, the agent cannot:
- Understand the full system
- Make changes safely
- Reproduce environments
- Reason about the impact of changes

**Red flags:**
- Database tables created through admin UIs
- Server configuration done via SSH and manual editing
- "It's documented in the wiki" instead of being in code
- Environment variables that exist only on production servers
- Build steps that require human judgment or intervention

**What good looks like:**
- Database migrations in code (e.g., Ecto migrations, Rails migrations, Flyway)
- Infrastructure as code (Terraform, Pulumi, CloudFormation)
- Configuration files checked into version control
- Docker/containerization for environment definition
- CI/CD pipelines defined in code (GitHub Actions, GitLab CI, etc.)

---

### 2. Fully Automated Build with No Manual Steps

**What this means:** Running a single command (or triggering a single pipeline) takes the codebase from source to deployable artifact with zero human intervention.

**Why it matters for AI agents:** An agent needs to verify its changes work. If building requires clicking through a GUI, copying files manually, or "you just need to remember to also do X," the agent cannot complete the feedback loop. The agent also cannot help you fix build issues if it can't run the build.

**Red flags:**
- Build instructions that include "then open the IDE and..."
- Manual file copying or renaming as part of the build
- Builds that only work on specific developers' machines
- Steps documented in wikis or tribal knowledge rather than scripts

**What good looks like:**
- `make build`, `npm run build`, `mix compile` - one command does everything
- Build runs identically in CI and on developer machines
- All dependencies fetched automatically
- Build output is deterministic (same inputs = same outputs)
- Lock files for all dependencies (package-lock.json, mix.lock, etc.)
- Containerized build environments for consistency

---

## Testing Infrastructure

### 3. Isolated, Self-Contained Database/Data Stores

**What this means:** Each developer and each test run has its own isolated database instance that can be created, populated, and destroyed automatically.

**Why it matters for AI agents:** An agent needs to run tests without fear of corrupting shared data or having tests fail due to state left by other processes. If your test database is shared or requires manual setup, the agent cannot:
- Run tests confidently
- Run tests in parallel
- Clean up after itself
- Reproduce failures

**Red flags:**
- Tests that fail randomly due to data from previous runs
- "Don't run the full test suite, it'll mess up the dev database"
- Manual database setup steps before running tests
- Tests that depend on specific data existing in a shared database

**What good looks like:**
- Database created/migrated automatically before tests
- Each test run starts with known state (fixtures, factories, seeds)
- Tests can run in parallel without interference
- Containers or temp databases spun up per test suite

---

### 4. Comprehensive Unit Tests

**What this means:** Individual functions, modules, and components have automated tests that verify their behavior in isolation.

**Why it matters for AI agents:** Unit tests are the fastest feedback mechanism. When an agent makes a change, it needs to know immediately if it broke something. Unit tests:
- Run in milliseconds to seconds
- Pinpoint exactly what broke
- Document expected behavior (the agent reads tests to understand intent)
- Enable safe refactoring

**Red flags:**
- "We test manually before releases"
- Tests that require external services to be running
- No tests for business logic
- Tests that take minutes to run individually

**What good looks like:**
- Tests for all business logic and algorithms
- Mocked external dependencies
- Tests runnable offline
- Clear test names that describe behavior
- Full unit test suite runs in under 2 minutes
- Tests can be filtered by file/tag/pattern

---

### 5. End-to-End Tests

**What this means:** Automated tests that exercise the full system as a user would - through the UI or API, hitting real databases and services (in isolated test environments).

**Why it matters for AI agents:** Unit tests verify components work in isolation; E2E tests verify they work together. An agent making changes across multiple layers needs confidence the integration still works. E2E tests also catch issues that unit tests miss - misconfigured routes, broken API contracts, UI regressions.

**Red flags:**
- "We do manual QA before each release"
- E2E tests that are flaky and ignored
- No way to run E2E tests locally
- E2E tests that take hours to run

**What good looks like:**
- Critical user journeys covered by automated tests
- E2E tests run in CI on every PR
- Tests can run locally with minimal setup
- Reasonable execution time (minutes, not hours)
- Slow tests separated from fast tests
- Parallel test execution where possible

---

## Code Quality and Conventions

### 6. Clear Project Structure and Conventions

**What this means:** The codebase follows consistent, predictable patterns for where things live and how they're organized.

**Why it matters for AI agents:** An agent navigating an unfamiliar codebase relies on conventions to find what it needs. If every developer organizes things differently, the agent wastes time searching and may miss important files. Consistent patterns enable:
- Faster navigation ("tests are always next to source files")
- Accurate assumptions ("API routes are in /routes")
- Appropriate placement of new code

**Red flags:**
- No consensus on file organization
- Similar functionality scattered across different patterns
- "You just have to know where things are"
- Naming conventions that vary by developer or era

**What good looks like:**
- Documented project structure (even a brief README section)
- Consistent naming patterns (files, functions, variables)
- Framework conventions followed (Phoenix contexts, Rails conventions, etc.)
- New code obviously belongs in a specific place

---

### 7. Automated Linting and Formatting

**What this means:** Tools automatically enforce code style and catch common errors, with configuration checked into the repository.

**Why it matters for AI agents:** Without automated formatting, an agent's changes create noisy diffs mixing style changes with substantive changes. Linters catch errors before runtime. When the agent produces code matching project style automatically:
- Code reviews focus on substance, not style
- Diffs show only meaningful changes
- Common errors caught immediately
- Agent output is consistent with existing code

**Red flags:**
- Style debates in code review
- Inconsistent formatting across files
- No static analysis catching obvious errors
- "We should set up a linter someday"

**What good looks like:**
- Formatter runs on save or pre-commit (Prettier, mix format, gofmt)
- Linter in CI blocks PRs with errors
- Shared configuration in repository
- Editor integrations for immediate feedback

---

## Environment and Dependencies

### 8. Environment Parity

**What this means:** Development, testing, staging, and production environments behave identically in all ways that matter.

**Why it matters for AI agents:** Code that works in development but fails in production is a nightmare to debug - for humans and agents alike. When environments differ, the agent cannot trust its local testing. Environment parity means:
- Bugs reproduce locally
- Fixes verified locally actually work in production
- No "works on my machine" surprises

**Red flags:**
- Different databases in dev vs prod (SQLite vs PostgreSQL)
- Features that only work in certain environments
- Environment-specific bugs that can't be reproduced locally
- "That only happens in production"

**What good looks like:**
- Same database engine across environments
- Docker/containers ensuring identical runtimes
- Environment variables documented and consistent
- Feature flags over environment-specific code

---

### 9. Actionable Error Messages and Logs

**What this means:** When things fail, error messages point to the root cause with enough context to fix the issue.

**Why it matters for AI agents:** An agent debugging an issue relies entirely on the information in error messages and logs. Cryptic errors like "Error: undefined" or stack traces without context force the agent to guess. Good error messages:
- Identify what went wrong
- Indicate where it went wrong
- Suggest what might fix it
- Include relevant context (input values, state)

**Red flags:**
- Generic error messages ("Something went wrong")
- Swallowed exceptions with no logging
- Logs that don't include request IDs or context
- Stack traces as the only error information

**What good looks like:**
- Errors include what was expected vs. what happened
- Structured logging with consistent formats
- Request tracing across services
- Errors actionable without reading source code

---

## Documentation

### 10. Accessible, Current Documentation

**What this means:** README files, inline comments, and API documentation that accurately reflect the current system.

**Why it matters for AI agents:** Documentation is often the first thing an agent reads to understand a codebase. Outdated documentation is worse than no documentation - it actively misleads. The agent benefits from:
- README explaining how to get started
- Architecture overview for navigation
- API docs for understanding interfaces
- Comments explaining non-obvious code

**Red flags:**
- README refers to deprecated approaches
- Comments describe what code used to do
- No documentation for getting started
- "The documentation is out of date, just ask Sarah"

**What good looks like:**
- README updated as part of relevant changes
- Generated API docs from code annotations
- Architecture decision records for major choices
- Comments explain "why" for complex logic

---

## Prioritization

If you're starting from scratch, prioritize in this order:

1. **Automated build** - This is the first level of feedback, and is core to everything else
2. **System in source code** - Get everything version controlled
3. **Isolated test databases** - Enable safe testing
4. **Unit tests** - Fastest feedback loop
5. **Linting/formatting** - Low effort, high consistency payoff
6. **Everything else** - Iterate based on pain points

Each item you address increases what an AI agent can do autonomously and reduces the friction in your development process - with or without AI assistance.
