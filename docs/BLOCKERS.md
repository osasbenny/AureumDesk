# AureumDesk Blockers

| ID | Category | Blocker | Workaround | Status |
|---|---|---|---|---|
| B001 | Telephony | Actual Nigerian number/carrier/PBX routing not yet supplied | Provider-neutral telephony adapter + mock IVR | Open |
| B002 | WhatsApp | Production Business Platform credentials/configuration not yet supplied | Mock WhatsApp adapter | Open |
| B003 | Scheduling | Centre's production scheduling system/API not yet confirmed | Mock appointment provider | Open |
| B004 | Staff routing | Approved secretary/department/MD destinations not yet supplied | Configurable placeholder destinations | Open |
| B005 | Knowledge | Approved Centre knowledge base not yet supplied | Demo/synthetic knowledge | Open |
| B006 | Healthcare policy | Production refill/escalation/privacy rules require Centre approval | Safe human-review workflow | Open |
| B007 | AWS | Production AWS account/resources may require setup/credentials | Infrastructure-as-code + deployment instructions | Open |

## Rule
A blocker must not stop independent implementation. Build a mock/adapter, document the exact required human input, and continue.