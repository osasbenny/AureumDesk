# AureumDesk

**Aureum AI Front Office** — a reusable, white-label AI front-office platform under Aureum / OpenAura.

> ChatGPT is the product/architecture brain. Manus is the implementation executor.

## Product
AureumDesk connects organizations to customers through channels such as phone and WhatsApp, routes intent through policy and approved knowledge, executes authorized actions through typed tools, confirms backend results and escalates to humans when needed.

**First vertical:** Healthcare  
**First prototype:** The Freudian Centre, Lagos, Nigeria  
**Repository:** https://github.com/osasbenny/AureumDesk

Healthcare functionality is administrative/support software. It does not autonomously diagnose, prescribe, change medication, authorize dispensing or make clinical decisions.

## Core pipeline
Channel → Core → Intent → Policy/Guardrails → Knowledge/Tools → Action → Confirmation → Human escalation

## Documentation
Start here:
1. docs/AUREUMDESK_MASTER.md — master product/engineering source of truth
2. docs/PRD.md — product requirements
3. docs/ARCHITECTURE.md — system architecture
4. docs/DESIGN.md — UX/design direction
5. docs/SECURITY.md — security and healthcare safety
6. docs/TEST_PLAN.md — verification strategy
7. docs/DECISIONS.md — architectural decisions
8. docs/MEMORY.md — persistent project context
9. MANUS.md — implementation-agent rules
10. RULES.md — project-wide engineering rules
11. TASKS.md — implementation backlog
12. CHANGELOG.md — verified repository save points

Supporting documentation is under docs/.

## Development
Use .env.example as the variable-name template. Never commit credentials, real patient/customer data or provider secrets.

Before declaring work complete:
- run tests;
- run lint;
- run typecheck;
- run production build;
- scan for secrets;
- review the diff;
- update documentation and changelog;
- verify Git status and commit/push state.

## Current state
The repository now contains the product and engineering documentation foundation. Implementation must be verified against repository state before any completion claim is made.

## Execution model
ChatGPT defines architecture, product behavior, safety boundaries and acceptance criteria. Manus inspects, implements, tests, documents, commits and pushes.

## License
License to be defined before commercial distribution.
