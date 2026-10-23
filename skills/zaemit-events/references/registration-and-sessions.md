# Registration events and conference programs

## Registration (`reg_*`)
- `reg_listEvents` (draft, open, closed, archived) / `reg_upsertEvent`. Without `event_seq` a new draft is created. Registrations are accepted only when the status is open and a registration type with prices exists.
- `reg_listRegistrations`, `reg_getRegistration`, `reg_stats`.
- `reg_setRegistrationStatus` is a confirmation tool and notifies registrants: `approve`, `reject`, `cancel` (operator cancellation), `confirm_offline_paid` (bank transfer received). Rejection and cancellation cannot be reversed.
- Cancelling a paid registration only records a refund request; the refund is run in the Zaemit admin screen.
- With several ids, one blocked registration does not stop the others; report which ones failed.

## Conference program (`session_*`)
- `session_listEvents`, then `session_getProgram` gives the `session_seq`, `day_seq`, track and room ids the other session tools take.
- `session_saveSession` without `session_seq` creates a draft session. Time is given in the event's local time or UTC. A session in the same room at the same time is rejected unless `force=true`; ask the user before forcing.
- Speakers: `session_listSpeakers` (invited, accepted, declined, material_submitted, confirmed).
