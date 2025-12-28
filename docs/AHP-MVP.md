# AHP-MVP (Minimal Viable Protocol)

## Purpose
Define the smallest coherent specification for a care-centered protocol that preserves identity, memory, and safe time while enabling accountable guardianship.

## Components
- **Identity**: A stable, user-controlled representation of the person.
- **Living Memory**: A chronological, user-legible record of meaningful events, with corrections recorded as new entries rather than overwrites.
- **Safe Time**: A deliberate pause state that reduces pressure and risk.
- **Error Log**: A bounded record of errors as events, not judgments. Errors may contribute to transition traces if they result in irreversible changes.
- **Guardian**: A role that bears duty of care without coercive power.
- **Exit/Return**: A clear, reversible path to leave and re-enter.

Note on storage:
AHP-MVP assumes a causal memory substrate (TTM DB — Traces of Time and Meaning) as the physical carrier for Living Memory and irreversible transitions.
TTM DB is not a generic event log and is out of scope for this MVP, but all components are designed to be compatible with it.

## Minimal data model
**Identity**
- `identity_id`
- `display_name`
- `consent_state`
- `created_at`

**Memory (Living Memory Entry)**
- `memory_id`
- `identity_id`
- `timestamp`
- `summary`
- `tags`
- `source` (self, guardian, system)

**Event (Error/Event Log)**
- `event_id`
- `identity_id`
- `timestamp`
- `event_type`
- `context`
- `resolution_state`

## Minimal scenario
**Day 1**
- Identity created with explicit consent state.
- First memory entry added by the person.
- Guardian role acknowledged with duty statement.

**Day 2–7**
- Memory grows with small, tagged entries.
- Safe Time is invoked at least once.
- An error event is logged and resolved.

**Day 14+**
- Exit is exercised once and return is successful.
- Memory remains intact and editable.

## Success criteria (no KPI)
- The person can explain their own record in plain language.
- Guardianship actions are visible and limited.
- Exiting and returning feels safe and non-punitive.

## Risks & anti-patterns
- Treating memory as surveillance or scoring.
- Forcing urgency or compliance during Safe Time.
- Guardian override without audit.
- Permanent labels from temporary errors.
- Incentivized performance or applause.
