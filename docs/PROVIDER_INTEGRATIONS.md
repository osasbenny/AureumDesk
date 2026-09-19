# Provider Integrations

AureumDesk must isolate vendor-specific code behind adapters.

## Telephony
Candidates: Twilio, Telnyx, Nigerian telecom/VoIP provider, SIP carrier.

## Voice AI
Candidates: Retell, Vapi, or another realtime provider.

## Speech
Provider-native STT/TTS, OpenAI audio, Deepgram or another approved provider.

## WhatsApp
Meta WhatsApp Business Platform, supported BSP or Twilio WhatsApp.

## Scheduling
Google Calendar, existing hospital system, custom API or mock provider.

## Human support
Chatwoot or a future AureumDesk inbox.

No provider should be so deeply coupled that replacing it requires rewriting AureumDesk Core.