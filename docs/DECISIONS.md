# AureumDesk Architecture Decision Record

## ADR-001 — Reusable vertical-agnostic core
Decision: Build AureumDesk Core as a reusable platform and keep healthcare behavior in configuration, policies and adapters.
Reason: AureumDesk is intended for white-label deployment across industries.

## ADR-002 — Modular monolith for MVP
Decision: Prefer a modular monolith over premature microservices.
Reason: Strong module boundaries are needed without distributed-system overhead.

## ADR-003 — AI is not the source of truth
Decision: The LLM may reason and select typed tools, but backend services remain authoritative.
Reason: AI output must not be treated as proof that a consequential action occurred.

## ADR-004 — Typed tools for actions
Decision: Consequential AI-triggered actions pass through typed, validated, authorized service interfaces.
Reason: Enforce security, auditability, idempotency and provider abstraction.

## ADR-005 — Provider adapters
Decision: Telephony, WhatsApp, scheduling, speech and voice AI providers are isolated behind interfaces.
Reason: Providers may vary by deployment.

## ADR-006 — Human handoff is first-class
Decision: Handoff is a core state transition, not only an error path.
Reason: Organizations require staff ownership for exceptions and sensitive requests.

## ADR-007 — Synthetic data during prototype
Decision: Development uses synthetic/test data until customer authorization and production controls exist.
Reason: Prevent accidental exposure of patient/customer data.

## ADR-008 — Healthcare administrative boundary
Decision: Healthcare deployment is limited to administrative/support workflows.
Reason: Diagnosis, prescribing, medication changes and clinical decisions are outside scope.

## ADR-009 — Configuration over customer hard-coding
Decision: Organization branding, hours, departments, routing, knowledge, policies and integrations are configuration.
Reason: New deployments should not require a fork of the core.

## ADR-010 — Managed AWS footprint
Decision: Use the smallest practical managed AWS footprint and add services only when justified.
Reason: Reduce operational complexity and cost while retaining a production path.
