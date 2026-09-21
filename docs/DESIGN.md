# AureumDesk Design System & UX Direction

Status: Foundation
Version: 1.0

## 1. Design objective
AureumDesk should feel premium, calm and trustworthy — not like a generic chatbot dashboard. It should communicate competence, transparency, control and easy human escalation.

## 2. UX principles
- Human-first: automation never hides the human path.
- Clear state: users know whether AI, staff or a provider is handling the interaction.
- Progressive disclosure.
- Confirmation before consequential actions.
- Evidence over unsupported claims.
- Accessible and responsive.
- Organization branding is configurable.

## 3. Core surfaces
### Public/demo
- Product overview
- Conversation/demo entry
- Service/channel explanation
- Trust and safety explanation

### Organization admin
- Dashboard
- Conversations
- Handoffs
- Appointments
- Knowledge
- Departments/staff routing
- Integrations
- Audit/events
- Settings

### Operations
- Live conversation queue
- Human takeover
- Provider status
- Failed actions/retries
- Audit trail
- Health/readiness

## 4. Conversation UX
Every conversation should expose channel, state, legitimate identity context, current intent, action status, human/AI ownership, relevant source/status, timestamped events and escalation controls.

AI messages must not imply an action happened until the backend confirms it.

## 5. Action UX
1. Collect required information.
2. Validate.
3. Present intended action.
4. Obtain required confirmation.
5. Execute through backend tool.
6. Display backend-confirmed result.
7. Write an audit event.

## 6. Visual language
Use a restrained Aureum visual identity with strong typography, generous spacing, subtle depth and clear status indicators. Avoid medical clichés, noisy dashboards and anthropomorphic claims about AI.

## 7. Accessibility
Target WCAG-aligned contrast, keyboard navigation, visible focus states, semantic controls, readable errors and mobile-friendly layouts.

## 8. White-label rule
Brand, terminology, organization details, hours, departments, policies, knowledge and enabled channels are configuration. Core safety controls are not customer-editable without engineering controls.
