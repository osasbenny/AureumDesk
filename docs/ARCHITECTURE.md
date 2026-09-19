# AureumDesk Architecture

AureumDesk is a reusable AI front-office platform. The first deployment is a healthcare configuration for The Freudian Centre, Lagos.

## Flow
Channel adapters -> AureumDesk Core -> Intent -> Policy/Guardrails -> Knowledge/Tools -> Action -> Confirmation -> Human handoff.

## Core modules
- API/webhook gateway
- Organization configuration
- Conversation/session service
- AI orchestration
- Policy/guardrails
- Knowledge service
- Tool/action service
- Appointment service
- Prescription-refill request service
- Handoff/routing service
- Notifications
- Audit/events
- Provider adapters

## Infrastructure
AWS-managed backend: PostgreSQL, containerized API, SQS/EventBridge where useful, S3, Secrets Manager, IAM and CloudWatch. Prefer a modular monolith for MVP and avoid unnecessary microservices.

## Rules
Provider-agnostic adapters; organization isolation; typed tool actions; secure secrets; synthetic development data; human escalation as a first-class capability; configurable vertical policies.