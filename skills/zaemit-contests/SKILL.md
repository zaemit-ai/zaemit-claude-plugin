---
name: zaemit-contests
description: Run a contest or award program on a Zaemit site. Use when the user wants to create or edit a contest, show the application, status or winners screen on a page, review entries, select entries for judging, or check judging results and contest statistics.
---

# Contests

Contests are a plugin (`plugin_install`).

## Workflows

### Open a contest
1. `contest_listContests` to avoid a duplicate.
2. `contest_upsertContest` creates a draft. Entries are accepted only while the status is `open`; open it when the user wants to take entries now.
3. `contest_embed` with `create_page=true` for the entry form (`apply`) and, when wanted, the status or winners screens.
4. `page_sections` on the main page to see where the screens went.
5. Report the contest name, the entry period and every page address.

### Pick entries for judging
1. `contest_listEntries`, `contest_getEntry`.
2. `contest_setEntryStage` for each chosen entry.
3. `contest_results` / `contest_dashboard` for the current picture.
4. Locking candidates, later rounds and publishing results are done in the Zaemit admin screen; say so when the user asks for them.

## Create and show
1. `contest_listContests` / `contest_getContest` to check existing ones.
2. `contest_upsertContest` without `contest_seq` creates a draft. Entries are accepted only while the status is `open`. `intake`, `schedule`, `sponsors`, `divisions`, `certificate` and `notify` are JSON strings.
3. `contest_embed` places a contest screen on a page; without `page_seq` it goes on the main page. `create_page=true` (apply, status, judge, winners) also makes a dedicated page linked from the header. After using it, check the main page with `page_sections` and tell the user where the screen appeared.
4. Award and competition blocks for building pages appear in `design_blocks` with `category=contest`.

## Entries and judging
- `contest_listEntries` (stages received, excluded, round1, round2, result, awarded), `contest_getEntry`.
- `contest_setEntryStage` selects, excludes or restores entries for judging; nothing changes once the judging candidates are locked.
- `contest_results` shows scores (final round unless `round_no`), `contest_dashboard` shows traffic, scoring and voting figures.
- Locking candidates, moving entries to later rounds and publishing results are done in the Zaemit admin screen.
- Participant details are masked unless raw access was allowed.
