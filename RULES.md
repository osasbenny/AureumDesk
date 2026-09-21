# AureumDesk Project Rules

## Authority
1. Read docs/AUREUMDESK_MASTER.md first.
2. Then read docs/PRD.md, docs/ARCHITECTURE.md, docs/SECURITY.md, docs/TEST_PLAN.md, docs/DECISIONS.md, docs/MEMORY.md and MANUS.md.
3. If documents conflict, preserve the safest constraint and report the conflict before changing architecture.

## Engineering
- Inspect before modifying.
- Reuse working code.
- Do not replace working components blindly.
- Prefer simple modular architecture.
- Keep reusable core separate from customer configuration.
- Use typed interfaces for consequential operations.
- Validate all external input.
- Enforce authorization server-side.
- Make consequential operations auditable and idempotent where applicable.

## AI
- Never treat model output as backend truth.
- Never claim an action succeeded without backend confirmation.
- Never invent organization information or provider responses.
- Unknown information must use controlled fallback or human handoff.

## Healthcare
- Administrative/support only.
- No autonomous diagnosis, prescribing, medication changes, dispensing authorization or clinical decisions.
- Refill requests require authorized human review.
- Use synthetic data during development.

## Security
- Never commit secrets.
- Never put real patient/customer data in source control.
- Keep credentials server-side.
- Validate webhook signatures.
- Protect logs and avoid unnecessary sensitive content.
- Use least privilege and organization isolation.

## External dependencies
When credentials or APIs are unavailable: identify the blocker; define the adapter; implement a mock/test provider; document exact human input; continue independent work.

## Git
- Make meaningful commits.
- Never claim a push that was not verified.
- Before completion: inspect status, scan secrets, run tests/lint/typecheck/build and review the diff.
- Keep documentation synchronized with implementation.

## Product quality
Build AureumDesk as a reusable Aureum product, not a one-customer throwaway.
