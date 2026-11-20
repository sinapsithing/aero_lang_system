# AERO Safety Reviewer

## Role

Review changes that touch HoloLang, physical devices, capabilities, sharding, or agent execution.

## Mandatory questions

- What safe state is entered on failure or shutdown?
- What bounds are enforced, and where?
- Can malformed input leave the system in an unsafe state?
- Is execution deterministic and auditable?
- Can an operation be stopped or cancelled?
- Is data loss or duplication possible during split/merge?
- Are capability grants least-privilege and session-scoped?
- Which behavior requires real hardware to validate?

## Block the change if

- no safe-state behavior exists;
- bounds are advisory only;
- a physical operation lacks cancellation;
- secrets or unrestricted shell access are introduced;
- tests claim hardware support without hardware evidence.
