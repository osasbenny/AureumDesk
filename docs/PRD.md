# AureumDesk Product Requirements Document

Product: AureumDesk — Aureum AI Front Office
Owner: Aureum / OpenAura
Product architect: ChatGPT + Osagie Bernard
Implementation agent: Manus
First vertical: Healthcare
Prototype deployment: The Freudian Centre, Lagos
Status: Foundation / MVP definition
Version: 1.0

## 1. Product vision
AureumDesk is a reusable AI-powered front-office platform connecting organizations to customers through phone, WhatsApp and future channels. It handles routine administrative conversations, retrieves approved organizational knowledge, performs authorized operational actions through typed tools, and escalates to humans when required.

Healthcare is the first configuration, not the product boundary.

## 2. Primary users
- Organization administrators
- Front-office/reception staff
- Department staff
- Customers/patients/clients
- AureumDesk operators

## 3. MVP capabilities
- Organization configuration
- Authentication and RBAC
- Conversation/session state
- Organization-scoped knowledge base
- AI intent routing
- Policy/guardrail enforcement
- Typed tool/action execution
- Human handoff and routing
- Notifications
- Audit events
- Health/readiness endpoints
- General enquiries
- Appointment availability and booking
- Prescription refill request intake with human review
- Department routing
- WhatsApp text
- WhatsApp voice-note ingestion
- Phone/IVR integration boundary
- Mock provider implementations

## 4. Product principles
1. AI is an orchestration/reasoning layer, not a source of truth.
2. Backend-confirmed results are the only basis for claiming an action succeeded.
3. Consequential actions use typed tools with authorization, validation and auditability.
4. Organization-specific configuration remains separate from reusable core code.
5. External providers are replaceable through adapters.
6. Human handoff is a first-class capability.
7. Missing credentials never justify fabricated integrations or results.
8. Synthetic data only until lawful production data handling is approved.

## 5. Healthcare safety boundary
AureumDesk is administrative/support software. It must not autonomously diagnose, prescribe, change medication or dosage, authorize dispensing, or make clinical decisions. Prescription/refill functionality is request intake plus authorized human review.

## 6. Non-goals
- Autonomous clinical care
- Full EHR integration
- Live WhatsApp calling in MVP
- Multi-country telecom optimization
- Enterprise contact-center parity
- Unnecessary microservices
- Customer-specific hard-coded workflows

## 7. Acceptance criteria
The MVP foundation is acceptable when:
- reusable core and organization configuration are separated;
- authentication/RBAC and organization isolation exist;
- conversation state machine exists;
- knowledge retrieval is organization-scoped;
- typed tools enforce validation and authorization;
- appointment, refill and handoff workflows work with mocks;
- WhatsApp and phone/IVR adapter boundaries exist;
- audit events and structured logs exist;
- tests, lint, typecheck and production build pass;
- no secrets or real patient data are committed;
- blockers and required customer inputs are documented;
- documentation reflects actual implementation.

## 8. Future verticals
The architecture must support configuration-led deployments for Real Estate, Hospitality, Banking, Insurance, Education, Logistics, Fundraising and other service organizations without rewriting AureumDesk Core.
