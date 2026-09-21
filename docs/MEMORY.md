# AureumDesk Project Memory

Purpose: Persistent project context for ChatGPT, Manus and future engineering sessions.

## Identity
- Product: AureumDesk
- Positioning: Aureum AI Front Office
- Parent: Aureum / OpenAura
- Repository: osasbenny/AureumDesk
- Product architect/brain: ChatGPT + Osagie Bernard
- Implementation agent: Manus

## Product truth
AureumDesk is a reusable AI front-office platform. Healthcare is the first vertical and The Freudian Centre is the first prototype deployment, not the permanent product definition.

## Core pipeline
Channel → AureumDesk Core → Intent → Policy/Guardrails → Knowledge/Tools → Action → Confirmation → Human escalation.

## Safety truth
Healthcare functionality is administrative/support only. No autonomous diagnosis, prescribing, medication changes, dispensing authorization or clinical decisions.

## Architecture truth
Preferred stack is TypeScript/Node.js, PostgreSQL, provider adapters, typed tools, REST/webhooks and AWS-managed infrastructure. Modular monolith is acceptable for MVP.

## External dependency truth
Customer-specific phone/PBX, WhatsApp credentials, scheduling APIs, staff routing, approved knowledge, privacy/security requirements and production AWS configuration must be obtained. Never invent them.

## Implementation truth
Missing external credentials should produce mocks/adapters plus documented requirements, not a stalled build.

## Documentation truth
docs/AUREUMDESK_MASTER.md remains the product/engineering source of truth. This memory file is a compact orientation layer and must not silently override the master document.

## Collaboration model
ChatGPT = architecture, reasoning, product direction, review and acceptance criteria.
Manus = repository inspection, implementation, testing, documentation updates, commits and pushes.

## Working rule
Any claim of completion must be backed by actual repository state, tests/build output and verified Git history.
