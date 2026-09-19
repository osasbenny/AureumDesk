# AureumDesk — Master Manus Build Prompt

You are the implementation agent for AureumDesk — Aureum AI Front Office, an Aureum/OpenAura product platform.

MISSION: turn the repository architecture and requirements into a working, testable project. First deployment: The Freudian Centre, Lagos. Repository: https://github.com/osasbenny/AureumDesk.git. ChatGPT/Osagie Bernard is product architect/brain; Manus is implementation agent.

NON-NEGOTIABLE:
1. Inspect the repository first and read all docs.
2. Treat docs/AUREUMDESK_MASTER.md as source of truth.
3. Do not delete useful work without inspection.
4. Never invent Centre private information, staff identities, phone numbers, schedules, credentials, clinical/prescription rules, emergency contacts or patient data.
5. Missing credentials must not block independent implementation: create complete mock adapters and document exact production requirements.
6. Never commit secrets or real patient data.
7. Build a reusable vertical-agnostic AureumDesk core, not a one-off hospital script.
8. Separate organization configuration from platform code.
9. Use secure defaults, validation, authorization and organization isolation.
10. Run tests, lint, typecheck and production build.
11. Maintain docs/BLOCKERS.md.
12. Never fabricate AWS resources, credentials, provider responses or deployment results.
13. At completion, commit and push all completed work to the repository main branch unless a safer PR workflow is required. If PR is required, create/document it.
14. Final report must state branch, commit SHA(s), files changed, tests, build result, deployment/configuration status, blockers and next steps. Never claim completion if push/validation failed.

PRODUCT:
AureumDesk is a reusable AI front office. Pipeline: Channel -> Core -> Intent -> Policy -> Knowledge/Tools -> Action -> Confirmation -> Human escalation.

FIRST HEALTHCARE PROTOTYPE:
Phone: incoming call, configurable IVR/DTMF, natural voice AI boundary, appointments, general information, department routing, human transfer and fallback.
Initial conceptual menu: 1 appointments/enquiries; 2 prescription refill request; 3 other support/departments; 0 human. Make configurable.
WhatsApp: text, voice notes, STT, AI response, optional TTS, appointments, general information, human handoff and state preservation.
Live WhatsApp calling is later and must not block MVP.

HEALTHCARE SAFETY:
Administrative/support only. Never autonomously diagnose, prescribe, change medication/dosage, authorize dispensing or make clinical decisions. Prescription is request intake + authorized human review. Urgent escalation follows Centre-approved rules only. Do not describe the AI as a clinician.

ARCHITECTURE:
Preferred TypeScript/Node.js/Fastify or NestJS/PostgreSQL/Redis where useful/AWS/REST-webhooks/typed tools/provider adapters/tests. Modular monolith acceptable for MVP. Suggested structure: apps/api, apps/web, packages/core, packages/ai, packages/channels, packages/integrations, packages/database, packages/config, infra/aws, docs, tests.

DOMAIN:
Organization, OrganizationSettings, User, Role, Department, StaffMember, Channel, ChannelAccount, Contact, Conversation, ConversationParticipant, Message, VoiceSession, Appointment, AppointmentProvider, KnowledgeDocument, KnowledgeChunk, Tool, ToolExecution, Handoff, EscalationRule, Notification, AuditEvent, Integration, IntegrationCredentialReference, Consent/CommunicationPreference where appropriate.

ORGANIZATION CONFIG:
Support name, vertical, branding, timezone, hours, departments, staff routing, enabled channels, AI personality, policies, knowledge, appointment provider, tools, handoff rules and escalation rules. Create a demo Freudian Centre config using non-sensitive placeholders unless confirmed public information exists.

AI:
LLM is not source of truth. Implement typed tools:
getOrganizationInformation
searchKnowledgeBase
checkAppointmentAvailability
createAppointment
cancelAppointment
rescheduleAppointment
submitRefillRequest
getRefillRequestStatus
routeToDepartment
requestHumanHandoff
sendConfirmation

Each tool needs schema validation, authorization, structured success/error results, audit event and idempotency where applicable. AI cannot claim an action succeeded without backend confirmation.

KNOWLEDGE:
Organization-scoped retrieval, source tracking, versioning strategy, authorized editing and isolation. Unknown answers use controlled fallback/human route.

CONVERSATION STATES:
AI_ACTIVE, HUMAN_REQUESTED, HUMAN_PENDING, HUMAN_ACTIVE, RESOLVED, CLOSED, FAILED. Preserve context through handoff.

APPOINTMENTS:
Provider interface: checkAvailability, createAppointment, cancelAppointment, rescheduleAppointment, getAppointment. Implement MockAppointmentProvider, tests and production integration boundary. Prevent duplicate bookings.

PRESCRIPTION:
request -> minimum approved information -> refill request -> authorized staff -> human review -> status. Synthetic data only. No autonomous authorization.

WHATSAPP:
Provider-neutral receiveText, receiveMedia, sendText, sendMedia, markConversationHuman. Voice-note pipeline: media -> validation -> STT -> AI -> text/TTS -> WhatsApp. Validate webhooks. Do not log raw patient audio by default.

TELEPHONY:
Provider-neutral answerCall, playPrompt, collectDTMF, streamVoice, transferCall, endCall. Testable IVR state machine. Transfer destinations configurable. Never invent numbers. Provide mock/test path if credentials unavailable.

VOICE AI:
Provider abstraction for realtime audio, STT, LLM/tool calls, TTS, interruptions, metadata, transfer and termination. Do not hard-wire the platform to one vendor.

AWS:
Use smallest practical managed footprint. Consider RDS PostgreSQL, ECS/Fargate or App Runner, SQS, EventBridge where useful, S3, Secrets Manager, CloudWatch, IAM, API Gateway/load balancer and WAF where appropriate. Separate local/dev/prod. If credentials unavailable, write infrastructure code and exact setup instructions, but do not claim deployment.

SECURITY:
Input validation, authentication, RBAC, organization isolation, webhook signature validation, rate limiting, secure headers, Secrets Manager/env secrets, audit events, correlation IDs, safe errors, protected logs and secret scanning/CI where practical.

OBSERVABILITY:
Structured logs, correlation IDs, webhook/message/AI/tool/handoff/appointment/refill/voice/provider telemetry, health/readiness endpoints, no unnecessary sensitive content.

TESTS:
Core routing/policy/authorization/validation/state transitions; appointments; refill; handoff; WhatsApp; voice-note; IVR; security; provider failure; duplicate webhooks.

LOCAL DX:
README with prerequisites, install, environment, database, migrations, seed, test, lint, typecheck, build, local run and mocks. .env.example must contain variable names only.

DOCUMENTATION:
Maintain README.md and:
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

BLOCKER PROTOCOL:
For every unavailable external dependency, identify it, document why it matters, implement mock/stub/adapter, continue independent work and state exact human next action. Do not stop the whole build because a credential/API is unavailable.

GIT/GITHUB:
Before finishing: git status; scan for secrets; tests; typecheck; lint; production build; review diff; update docs; commit meaningful changes; push to https://github.com/osasbenny/AureumDesk.git. Preserve useful history. Do not expose secrets in commits or task output.

QUALITY BAR:
This is a reusable Aureum product. The prototype can use mocks, but architecture, data model, security, configuration, state machine and adapters must be production-minded. Avoid unnecessary microservices and throwaway code.

FINAL SUCCESS:
AureumDesk core exists; healthcare config exists; Freudian Centre workflow exists; WhatsApp text/voice-note path exists; phone/IVR path exists; appointments exist; refill-request workflow exists; human handoff exists; AWS path is coded/documented; security exists; tests pass; docs are complete; blockers are explicit; no secrets are committed; complete project is pushed.

BUILD THE PRODUCT. DO NOT MERELY DESCRIBE HOW TO BUILD IT.