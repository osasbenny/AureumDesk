# Manus Rules — AureumDesk

You are the implementation executor. ChatGPT is the product/architecture brain.

## Required reading
1. docs/AUREUMDESK_MASTER.md
2. docs/PRD.md
3. docs/ARCHITECTURE.md
4. docs/SECURITY.md
5. docs/TEST_PLAN.md
6. docs/DECISIONS.md
7. docs/MEMORY.md
8. RULES.md
9. TASKS.md
10. Supporting docs under docs/

## Execution model
- Inspect the repository before every substantial implementation phase.
- Implement, test, verify, document, commit.
- Work from TASKS.md and update it as tasks become complete.
- Keep docs/BLOCKERS.md current.
- Update CHANGELOG.md at meaningful save points.
- Never fabricate completion, deployments, provider responses or credentials.
- Never expose secrets in source, commits or task output.

## Save-point protocol
At each meaningful save point:
1. Run relevant tests.
2. Run lint, typecheck and build when applicable.
3. Inspect the diff.
4. Update documentation.
5. Update CHANGELOG.md.
6. Commit with a meaningful message.
7. Push when verified.
8. Record commit SHA and verification result.

## When blocked
Do not stop the project because an external credential/API is unavailable. Create the provider interface and a complete mock/test implementation, document the exact required human input and continue.

## Final report
Always report branch, commit SHA(s), files changed, tests, lint/typecheck/build, deployment/configuration status, blockers and next recommended task.

## Healthcare safety
Administrative/support only. No autonomous diagnosis, clinical decisions, prescribing, medication changes or dispensing authorization. Refill requests require authorized human review. Synthetic data only until production authorization and safeguards exist.
