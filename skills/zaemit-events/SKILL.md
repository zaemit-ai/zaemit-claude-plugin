---
name: zaemit-events
description: Run events on a Zaemit site. Use when the user manages a networking or business-matching event, its participants and check-in, a paid registration event, a conference program with sessions and speakers, or an event budget.
---

# Events

Zaemit has three event features. Pick by what the user runs:

| The user runs | Tools | Notes |
|---|---|---|
| Networking or business matching (participants meet each other) | `event_*` | `kind` (matching or networking) is fixed at creation |
| Paid or approved registration (tickets, fees) | `reg_*` | See `references/registration-and-sessions.md` |
| Conference program (days, tracks, rooms, sessions, speakers) | `session_*` | Program events, days, tracks and rooms are created in the admin screen |
| Budget of an event | `budget_listBooks`, `budget_getSummary` | Read only; books are created and closed in the admin screen |

Selling seats or time slots as bookings is a reservation (zaemit-reservations), not an event.

## Workflows

### Open a networking or matching event
1. Ask what is essential and missing: matching (companies) or networking (individuals), since `kind` cannot change later; the dates; open or approval registration.
2. `event_upsertEvent` creates a draft. Registration works only while the status is `open`; set `status=open` with `event_upsertEvent` when the user wants to take registrations now.
3. `event_embed`: the participant app on a dedicated page, or participant cards on the home page.
4. Report the event name, dates, registration mode, status and page address.

### Add a session to a conference program
1. `session_listEvents`. When there is no program event, stop: program events, days, tracks and rooms are created in the Zaemit admin screen. Tell the user what to create there.
2. `session_getProgram` for the day, track and room ids.
3. `session_saveSession` creates a draft session.
4. Report the session time, room and status.

### Take paid or approved registrations
1. `reg_upsertEvent` creates a draft event.
2. Registration types with prices, consent text and placing the registration screen on a page are done in the Zaemit admin screen. Say so instead of reporting the event as ready.

## Networking and matching events
1. `event_listEvents` / `event_upsertEvent`. Without `id` a new draft matching event is created. Registration, meeting requests and messages work only while the event is open.
2. `event_embed` places the event app, a participant directory or content cards on a page; without `page_seq` it goes on the main page.
3. Participants: `event_listParticipants`, `event_getParticipant`.
4. `event_setParticipantStatus` is a confirmation tool and notifies participants. Rejection and blocking cannot be reversed, and in matching events they cancel ongoing meetings. Show the user who will be changed and wait for their yes.
5. Check-in: `event_checkinParticipant`; `undo=true` removes a check-in.

Participant details are masked unless raw access was allowed.
