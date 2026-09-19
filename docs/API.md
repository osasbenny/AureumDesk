# AureumDesk API Direction

The API should expose organization-scoped, authenticated endpoints and webhook handlers.

Core resource groups:
- organizations
- conversations
- messages
- knowledge
- appointments
- refill-requests
- handoffs
- departments
- notifications
- integrations
- health/readiness

External providers should enter through validated webhooks/adapters. Internal actions should use typed service interfaces rather than letting the LLM directly manipulate databases.