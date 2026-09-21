# AureumDesk Test Plan

Version: 1.0
Status: Foundation

## 1. Test strategy
Testing follows: Channel → Core → Intent → Policy → Knowledge/Tools → Action → Confirmation → Human Handoff.

Release gate: tests + lint + typecheck + production build.

## 2. Unit tests
Cover intent routing, policy checks, authorization, organization isolation, schemas, state transitions, handoff, appointment validation, duplicate prevention, refill states, typed tool contracts and configuration validation.

## 3. Integration tests
Cover database persistence, migrations/seed, webhook validation, idempotent webhooks, mock appointment provider, mock WhatsApp, mock telephony, AI tool invocation, audit events and notifications.

## 4. End-to-end scenarios
1. General enquiry answered from approved knowledge.
2. Unknown enquiry uses controlled fallback/human.
3. Appointment availability check.
4. Successful appointment booking.
5. Duplicate booking prevention.
6. Appointment provider failure.
7. Refill request routed to authorized human review.
8. Explicit human request.
9. Staff takeover with preserved context.
10. WhatsApp text lifecycle.
11. WhatsApp voice note to STT boundary to AI to response.
12. IVR routing and human transfer.
13. Failed transfer fallback.
14. Duplicate webhook does not duplicate action.
15. Cross-organization access is rejected.

## 5. Security tests
- Unauthorized tool execution
- Broken authorization
- Cross-tenant access
- Malformed input
- Invalid webhook signatures
- Replay/idempotency failures
- Rate limiting
- Secret exposure in logs
- Unsafe error responses

## 6. Reliability tests
Provider timeout, provider 5xx, retries, queue failure, database failure boundary, notification failure and safe human fallback.

## 7. Test data
Use synthetic organizations, contacts, conversations, appointments and refill requests. Never import real patient records into development or test environments.

## 8. Release checklist
- [ ] Unit tests pass
- [ ] Integration tests pass
- [ ] E2E scenarios pass
- [ ] Security tests pass
- [ ] Lint passes
- [ ] Typecheck passes
- [ ] Production build passes
- [ ] Secret scan passes
- [ ] Documentation matches implementation
- [ ] Blockers are current
