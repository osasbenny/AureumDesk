# AureumDesk Task Plan

## Phase 0 — Foundation
- [ ] Inspect repository and establish implementation baseline
- [ ] Establish package/app structure
- [ ] Establish environment configuration
- [ ] Establish database schema/migrations/seed
- [ ] Establish test/lint/typecheck/build tooling
- [ ] Establish authentication and RBAC
- [ ] Establish organization isolation
- [ ] Establish audit-event foundation

## Phase 1 — Core
- [ ] Organization configuration
- [ ] Conversation/session state machine
- [ ] Knowledge model and retrieval interface
- [ ] Intent routing
- [ ] Policy/guardrail engine
- [ ] Typed tool framework
- [ ] Human handoff/routing
- [ ] Notifications
- [ ] Health/readiness endpoints

## Phase 2 — Healthcare prototype
- [ ] General enquiry workflow
- [ ] Appointment mock provider
- [ ] Appointment availability/booking
- [ ] Cancellation/rescheduling boundary
- [ ] Refill request workflow with human review
- [ ] Department routing
- [ ] Synthetic Freudian Centre configuration

## Phase 3 — Channels
- [ ] WhatsApp provider adapter
- [ ] WhatsApp text flow
- [ ] WhatsApp media/voice-note flow
- [ ] STT/TTS abstraction
- [ ] Telephony provider adapter
- [ ] Configurable IVR/DTMF state machine
- [ ] Voice AI abstraction
- [ ] Human transfer/fallback

## Phase 4 — Production path
- [ ] AWS infrastructure definition
- [ ] Secrets/configuration strategy
- [ ] Observability
- [ ] CI/security scanning
- [ ] Deployment documentation
- [ ] Backup/rollback guidance

## Phase 5 — Verification
- [ ] Unit tests
- [ ] Integration tests
- [ ] E2E tests
- [ ] Security tests
- [ ] Lint
- [ ] Typecheck
- [ ] Production build
- [ ] Secret scan
- [ ] Documentation audit
- [ ] Final Git verification

See docs/BLOCKERS.md for external dependencies. Blockers must not stop independent work.
