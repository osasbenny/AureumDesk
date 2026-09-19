# AureumDesk Testing

## Unit
Intent routing, policy checks, tool authorization, validation, state transitions, appointments and handoff.

## Integration
Database, webhooks, mock scheduling, mock telephony, mock WhatsApp and AI tool calling.

## End-to-end
General enquiry; appointment request; unavailable slot; successful booking; refill request; human request; unknown answer; provider outage; duplicate webhook; staff takeover; failed transfer.

## Security
Unauthorized tool execution, cross-organization access, invalid webhook signatures and malformed inputs.

## Release gate
Tests, lint, typecheck and production build must pass before the implementation is declared complete.