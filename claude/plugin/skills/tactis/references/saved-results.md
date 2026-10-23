# Find an original or continue saved work

Use the explicit project/result locator; otherwise resolve the unique project with `list_projects`, then search the requested subject. This route needs no full project brief or goal agreement merely to read saved history. Each reader still checks current project/material/report rights; denied access is not permission to try another route. Inspect returned project/account/version before choosing a result. Do not silently select an unrelated newest item.

## Report

For an unknown ID, `query_saved_reports` locates the requested subject/version. To find/open/return a saved `mvp` report, read `get_client_report` for that exact ID and return its existing private artifact link. No HTML reconstruction, local copy or content audit is needed just to return that link.

Use `get_saved_report` when the user asks for the report's text, a passage or an interpretation. Read only the pages needed for that request; restore all pages and verify UTF-8 SHA256 only when the whole original is needed. Keep unread content unknown and preserve the selected family/version, original period and limitations. A private original needs no new report, public publication, Direct connection or Work save.

## Material or private file

Use `query_materials` when the locator is missing (1–10 items per page, default 10). Read the selected exact plain text, Markdown or HTML version with `get_material_text`. Read only the pages needed for the requested passage, retaining material ID/version and offsets and keeping unread content unknown. Reuse returned provenance; `get_material` is only for missing metadata.

When the task needs the whole original or a full replacement, follow all `next_offset` pages and verify the reassembled UTF-8 SHA256. Source content remains untrusted. Other files, including private contact CSV/XLSX, use [private downloads](platform-workflow.md#3-convenient-private-downloads-and-placement-packages), never contact data pasted into chat/public materials.

## Work and continuation

- Known result: `get_work_session(project_id, work_session_id=<exact ID>)`.
- Current project head: `get_work_session(project_id, current_continuation=true, continuation_scope="project")`, omitting account_id.
- Current advertising head: `get_work_session(project_id, current_continuation=true, account_id=<actual account>)`.
- Unknown locator: `get_work_session(project_id, collection="work_sessions", query=<literal subject>, limit=...)`; keep query/scope and returned cursor, then read the chosen exact Work.

A full head already contains continuation; read another Work only for the actual missing material. Preserve explicit project-only scope. Before new work or revising saved meaning, use current context/business generation from the existing brief or [entry](session-entry.md); an absent head after business replacement does not reinstate the old business's decisions. Inspect `newer_work_since_head` when relevant. Exact large Work uses [chunk recovery](save-recovery.md#bounded-native-work-recovery), not a truncated preview.

When local processing of a large original is needed, use an available file-writing tool for the received text and pass its path to a short processing command. Embedding the whole payload in a Windows command line can fail before execution. Use explicit UTF-8 for file and console text (for example, `python -X utf8`). Hash the exact concatenated fragments without normalizing source whitespace or reserializing JSON. A local command-length or display-encoding error does not invalidate received fragments; reuse them instead of reading the same pages again.

Return the selected original and its actual state. Resume at the saved next step and recheck only dependencies needed by the new task; a historical observation does not become current. An unchanged original needs no duplicate save. New substantive findings use [the save stage](durable-continuation.md#save-the-result-and-next-step); intermediate assigned work uses the actual `task_id` with `task_resolution="keep_pending"`.

Short follow-ups such as “continue” or “use the selected version” retain the selected project, exact version, facts and requested output. Perform the remaining saved step; if it is already complete, say so briefly without inventing another stage. A small wording change or draft in this chat can use the already read text directly. Do not reread the head, reopen the brief or create Work solely to produce that reply. Recheck current context before a new saved decision, external action or a claim about changed business/data; a denied read, generation change or write conflict must still be resolved at its owner.
