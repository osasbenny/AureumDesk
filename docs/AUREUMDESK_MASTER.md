# AureumDesk — Aureum AI Front Office
## Master Product & Engineering Document

Status: Initiated
Version: 0.1
Date: 2026-09-19
Product family: Aureum / OpenAura
First vertical: Healthcare
First prototype: The Freudian Centre, Lagos
Repository: https://github.com/osasbenny/AureumDesk.git
Implementation agent: Manus
Product architecture: ChatGPT + Osagie Bernard

## 1. Vision
AureumDesk is a reusable AI-powered front-office/customer-operations platform. It sits between an organization and its customers and unifies voice, IVR, WhatsApp, future web/social/email channels, organization knowledge, business tools and human escalation.

Core pipeline:
Channel -> AureumDesk Core -> Intent -> Policy/Guardrails -> Knowledge/Tools -> Action -> Confirmation -> Human escalation.

Future verticals include Healthcare, Real Estate, Hospitality, Banking, Insurance, Education, Logistics, Retail, Professional Services and Fundraising.

Positioning:
"AureumDesk — Aureum AI Front Office"
"The intelligent front office for modern businesses."

## 2. Product strategy
The core engine must be vertical-agnostic. Individual deployments are configurations of the engine.

Examples:
- Healthcare Edition
- Real Estate Edition
- Hospitality Edition
- Banking Edition
- Insurance Edition
- Education Edition
- Logistics Edition
- Fundraising Edition

Organization configuration includes brand, business information, timezone, hours, departments, staff routing, knowledge base, policies, escalation rules, channels, tools and integrations.

Never hard-code The Freudian Centre into reusable platform logic.

## 3. First deployment — The Freudian Centre
The first prototype is a healthcare administrative/support assistant for The Freudian Centre in Lagos. The founder previously worked with the Centre and the MD had asked about a system of this nature approximately five years ago. The strategy is to demonstrate a working prototype rather than begin with a conventional sales pitch.

### Phone
- Incoming call handling
- Configurable IVR
- DTMF input
- Natural-language AI voice integration
- Appointment enquiries
- General information
- Department routing
- Human transfer
- Failure/fallback

Initial conceptual menu:
1 = appointments/enquiries
2 = prescription refill request
3 = other support/departments
0 = human

Exact menu, staff destinations and escalation rules must be confirmed by the Centre.

### WhatsApp
- Text conversations
- Voice-note ingestion
- Speech-to-text
- AI response
- Optional generated voice response
- Appointment support
- General information
- Human handoff
- Staff notification
- Conversation state preservation

Live WhatsApp calling is a later capability and must not block MVP.

## 4. MVP scope
Must have:
- Reusable backend foundation
- Organization configuration
- Knowledge retrieval
- AI intent routing
- Typed tool architecture
- WhatsApp text workflow
- WhatsApp voice-note workflow
- Phone/IVR integration boundary
- Voice-agent abstraction
- Appointment availability and booking interface
- Human handoff
- Department routing
- Staff authentication/authorization
- Audit/event logging
- Error/retry handling
- Environment configuration
- Local mode
- Mock/test mode
- AWS deployment code/documentation
- Automated tests
- Complete repository documentation

### Healthcare workflows
General information must come only from approved organization knowledge.

Appointment workflow:
identify intent -> collect required information -> query provider -> offer slots -> confirm -> create booking -> confirm result -> audit.

Prescription workflow:
request intake -> collect minimum approved information -> create refill request -> route to authorized staff -> human review -> status.
The AI must not autonomously renew, change medication/dosage, authorize dispensing or make clinical decisions.

Human handoff:
support Secretary/Reception, departments, designated queues and approved escalation paths. Never invent contact numbers or identities.

## 5. MVP non-goals
Do not let these block the first prototype:
- Full EHR integration
- Autonomous diagnosis
- Autonomous clinical advice
- Autonomous prescription renewal
- Complex insurance claims
- Live WhatsApp calling
- Full enterprise contact-centre features
- Every social channel
- Multi-country telecom optimization
- Advanced analytics

Build clean extension points.

## 6. Technical architecture
Preferred:
- TypeScript
- Node.js
- Fastify or NestJS
- PostgreSQL
- Redis where useful
- AWS-managed infrastructure
- REST/webhooks
- Typed tool interfaces
- Provider adapters
- Automated tests

Recommended modular structure:
apps/api
apps/web
packages/core
packages/ai
packages/channels
packages/integrations
packages/database
packages/config
infra/aws
docs
tests

A modular monolith is acceptable for MVP. Avoid unnecessary microservices.

## 7. AWS direction
Use the smallest practical managed AWS footprint.

Potential services:
- RDS PostgreSQL
- ECS/Fargate or App Runner
- SQS
- EventBridge where useful
- S3
- Secrets Manager
- CloudWatch
- IAM
- API Gateway or load balancer
- WAF where appropriate

Separate local, development/test and production. Never commit secrets. If AWS credentials are unavailable, write infrastructure code and exact deployment instructions; never fabricate deployment.

## 8. Core data model
Support:
Organization
OrganizationSettings
User
Role
Department
StaffMember
Channel
ChannelAccount
Contact
Conversation
ConversationParticipant
Message
VoiceSession
Appointment
AppointmentProvider
KnowledgeDocument
KnowledgeChunk
Tool
ToolExecution
Handoff
EscalationRule
Notification
AuditEvent
Integration
IntegrationCredentialReference
Consent/CommunicationPreference where appropriate.

Healthcare-specific data must remain extensible rather than making the core healthcare-only.

## 9. AI/tool architecture
The LLM is a reasoning component, not the source of truth.

Typed tools should include:
- getOrganizationInformation
- searchKnowledgeBase
- checkAppointmentAvailability
- createAppointment
- cancelAppointment
- rescheduleAppointment
- submitRefillRequest
- getRefillRequestStatus
- routeToDepartment
- requestHumanHandoff
- sendConfirmation

Every tool requires schema validation, authorization, structured success/error results, audit event and idempotency where applicable.

The AI must never claim an action succeeded without backend confirmation.

## 10. Knowledge
Organization-scoped knowledge with:
- source tracking
- versioning strategy
- authorized editing
- retrieval
- isolation

Organization-specific answers should come from authoritative organization knowledge. If unavailable, use a controlled fallback and human route.

## 11. Conversation state
Use explicit states:
AI_ACTIVE
HUMAN_REQUESTED
HUMAN_PENDING
HUMAN_ACTIVE
RESOLVED
CLOSED
FAILED

Handoff preserves conversation ID, channel, available identity, reason, summary, collected fields, destination, timestamp and status.

## 12. Security
Never commit API keys, AWS credentials, OAuth secrets, database passwords, webhook secrets, phone/WhatsApp credentials, patient data or real conversations.

Implement:
- environment variables/Secrets Manager
- least-privilege IAM
- HTTPS
- webhook signature verification
- input validation
- rate limiting
- staff authentication
- RBAC
- organization isolation
- audit logs
- safe errors
- protected logs
- configurable retention/deletion

Use synthetic data only during prototype development.

## 13. Healthcare safety
AureumDesk Healthcare is administrative/support software. It must not autonomously diagnose, prescribe, change medication, authorize dispensing or make clinical decisions.

Urgent escalation must follow Centre-approved rules. Do not invent emergency contacts, clinical thresholds, guarantees or staff identities.

## 14. Provider strategy
Use replaceable adapters.

Telephony candidates: Twilio, Telnyx, Nigerian telecom/VoIP provider, SIP carrier.
Voice AI: Retell, Vapi or another realtime provider.
Speech: provider-native, OpenAI audio, Deepgram or other approved provider.
WhatsApp: Meta WhatsApp Business Platform, BSP or Twilio WhatsApp.
Scheduling: Google Calendar, existing hospital software, custom API or mock provider.
Human support: Chatwoot or custom AureumDesk inbox.

Do not make the platform dependent on one provider.

## 15. Human handoff
First-class handoff service with states and routing. Preserve context. Create provider-neutral interfaces. Mock support queue is acceptable for MVP.

## 16. Appointment architecture
Create provider interface for:
checkAvailability
createAppointment
cancelAppointment
rescheduleAppointment
getAppointment

Implement a mock provider plus tests and a production integration boundary. Design against duplicate bookings.

## 17. WhatsApp architecture
Provider-neutral functions:
receiveText
receiveMedia
sendText
sendMedia
markConversationHuman

Voice-note flow:
WhatsApp voice note -> media retrieval -> validation -> STT -> AureumDesk AI -> text and/or TTS -> WhatsApp response.

Validate webhooks. Do not log raw patient audio by default.

## 18. Telephony architecture
Provider-neutral functions:
answerCall
playPrompt
collectDTMF
streamVoice
transferCall
endCall

Testable IVR state machine:
incoming call -> welcome -> DTMF -> route -> AI/human -> action -> confirmation -> end/transfer.

Transfer destinations must be configuration-driven.

## 19. Observability
Use structured logs and correlation IDs. Track webhooks, messages, AI requests, tool execution/failure, handoffs, appointment actions, refill requests, voice sessions and provider errors. Add health/readiness endpoints. Avoid unnecessary sensitive data in logs.

## 20. Testing
Unit tests: intent routing, policies, authorization, validation, appointments, state transitions.
Integration tests: database, webhooks, mock scheduling, mock telephony, mock WhatsApp, AI tool calling.
E2E scenarios: general enquiry, appointment request, unavailable slot, successful booking, refill request, human request, unknown answer, provider outage, duplicate webhook, staff takeover, failed transfer.

## 21. Prototype data policy
Use synthetic patients, fictional appointments, mock prescription records and test accounts/numbers. Never load real patient records into development.

## 22. Blocker management
Maintain docs/BLOCKERS.md with:
ID, category, description, why it matters, workaround, required human input, impact, status.

Likely blockers:
- real phone/carrier routing
- WhatsApp credentials
- scheduling API
- staff routing destinations
- approved organization knowledge
- privacy/security requirements
- production domain
- AWS account/billing configuration

Missing credentials must result in mocks/adapters, not an unfinished project.

## 23. Documentation required
README.md
docs/AUREUMDESK_MASTER.md
docs/MANUS_BUILD_PROMPT.md
docs/ARCHITECTURE.md
docs/REQUIREMENTS.md
docs/API.md
docs/AWS_DEPLOYMENT.md
docs/SECURITY.md
docs/TESTING.md
docs/BLOCKERS.md
docs/FREUDIAN_CENTRE_PILOT.md
docs/PROVIDER_INTEGRATIONS.md
docs/OPERATIONS.md

Documentation must match actual implementation.

## 24. Definition of done
Buildable repository; local setup; migrations/seed; AI orchestration with provider or mock; WhatsApp adapter; voice/IVR adapter; appointment workflow; refill request workflow; handoff state machine; organization configuration; tests; no secrets; AWS path; documentation; blockers; clean commits; complete project pushed to osasbenny/AureumDesk.

## 25. IP and product principle
AureumDesk is reusable Aureum IP. Customer-specific configuration/data belongs to the deployment. Do not copy customer data into reusable fixtures.

Build the first prototype as if AureumDesk will have a second customer.

Build reusable engine + healthcare configuration, not a one-off Freudian Centre script.

## 26. Future ecosystem
AureumDesk may later connect to other Aureum products through APIs and clean boundaries, including AuraReach for acquisition, AuraPOS for transactions and AURA for fundraising. Do not turn the ecosystem into a monolith.

## 27. Immediate execution
1. Inspect repository.
2. Establish docs and project foundation.
3. Build reusable core.
4. Build local/mocks.
5. Organization configuration.
6. AI/tool framework.
7. WhatsApp text/voice-note.
8. Telephony/IVR.
9. Appointment workflow.
10. Refill workflow.
11. Human handoff.
12. Tests/observability.
13. AWS infrastructure path.
14. Validation.
15. Update blockers/docs.
16. Commit and push.

Current status: architecture/documentation initiated; implementation pending.