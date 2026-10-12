# Current account and action paths

Use the actual current tools and operation schema. Native campaign, group, ad and keyword IDs are decimal strings on the MCP wire. Preserve every digit; never convert them to JavaScript numbers. Owner fingerprints and immutable receipts retain their original representation; do not recompute their identities from a reformatted display response.

For a connected diagnosis → selected improvement or SEARCH draft → status/result return, use [the Ads workflow](ads-workflow.md). It supports both independent entry branches and reuses the exact action/recovery procedures below.

## How is my advertising doing?

Use [session entry](session-entry.md) for the client and [addressed foundation reads](foundation-reads.md#addressed-questions) for an ordinary status question. A full inventory, landing inference or current Ads action is needed only when the user's task or a relevant evidence gap calls for it. Save a substantive result through [durable continuation](durable-continuation.md); ordinary Work remains supported even when the current-head feature is absent.

## Change an existing campaign

### Inputs before a proposal

| Input / enforced prerequisite | Actual source | If missing or rejected |
| --- | --- | --- |
| Selected operation and complete supported payload | `get_operations_catalog(project_id, account_id, operation=..., include_schema=true)` | Save useful material with its missing capability; do not submit raw provider fields. Catalog availability is not object-shape validation. |
| Current account/selected object ancestry | Actual `prepare_native_scope` → `get_native_scope` | Preserve exact returned proof_id/mode/source; creator_account has no existing-target authority. |
| object_id / expected_version and full before-set | `get_native_configuration.current_provider_state.objects` and all needed exact family pages | Legacy `get_provider_state` versions, publication fingerprints and guessed integers are not substitutes. Complete replacement semantics require the complete set. |
| Native analysis_basis | Exact current Analysis publication/fingerprint and scope proof; `get_analysis_campaign_reference` / `get_dossier_campaign_reference` where the subject is used | `facts_id` equals its analysis_publication_id for modern proposals; this is separate from Work legacy facts_ids. No fabricated data.1 snapshot. |
| Creative source and URL | Exact landing manifest final_url, artifact_id/fingerprint and selected spans | copy.evidence_ids holds retained object IDs; landing_source.evidence_refs holds spans. Preserve meaningful destination identity. |
| Confirmed context / financial values | Current needed `get_business_context`; selected catalog money_policy_requirement and actual funding/provider evidence | No inferred versions, VAT, funding or launch target. Native PAUSED Creator also requires its finite money policy; use [launch prerequisites](campaign-launch.md#resolve-financial-and-measurement-prerequisites-before-a-plan). |
| Current operation rights | Operation-specific backend check and actual own access/connection readiness | Work access is separate. Correct the named prerequisite through its supported human path; no grant widening or legacy bypass. |

These sources assemble a schema-valid proposal; current state still decides admission. After freeze/read, preserve **chat-choice → exact execute → per-object readback** under [shared gates](invariants.md).

Read the exact existing group, keywords, negatives and relevant ads, completing every needed page. Pin fresh native scope and current object versions for the objects to be changed. A multi-title ad can be unsupported while a group-level negative change is supported; inspect per-object availability rather than treating every configuration family as writable. Do not flatten an unsupported ad to a single title or infer a writable version from a D1 fingerprint.

The catalog's `write_readiness` describes server/connection configuration, separately from object shape and the user's choice in chat. Its `legacy_connection_writes_enabled` flag concerns the old unscoped path; it is not the authority for a modern native-scoped operation. An operation-specific refusal remains binding even when `live_writes_enabled=true`.

Work access does not prove permission to freeze an Ads plan. For a refused proposal retain the useful draft and the returned reason: project/account access, scope, role or expired subscription may need the corresponding human setting. An unspecified `workspace_authorization_denied` leaves the particular cause unknown; do not widen permissions or bypass it through another path.

`get_operations_catalog` defaults to compact capabilities and readiness. For the selected operation's exact proposal contract, pass its operation name and include_schema=true; other operations are excluded from that schema, while unsupported refinements and money/scope limits remain binding. Do not request a whole catalog schema or infer that an advertised operation supports every provider object.

`get_operations_work` pages default to ten rows per collection; requests above ten require one collection. A byte-limited page may include fewer rows than requested and reports page_limited_by with the actual next_offset. If an aggregate page gives zero rows for a collection, read that collection at its unchanged offset. Recovery task title/description are bounded and explicitly mark truncation; retain the task and parent plan/Application IDs even before Workspace delivery. These Ads pages are separate from Workspace `get_work_session` collections.

For modern operations, supply `analysis_basis` with the exact current analysis publication ID/fingerprint and native scope proof ID when required by the actual tool schema. Do not fabricate a data.1 snapshot or old binding as `facts_id`. Preserve unchanged keyword/negative sets under replacement semantics. Prepare a PAUSED ad variant where supported. Freeze the proposal with `propose_operations` and read it with `get_operations_plan`. Show the exact change, consequences and limits in chat; ask the user to choose and wait before `execute_operations` with the saved plan ID and digest. Inspect Application and readback afterwards; never blindly retry an uncertain effect.

### Recover a lost execution response

Keep the original project, plan ID, digest and the Plan's original `proposal.command_key`. When all are known, call **`replay_operations(project_id, plan_id, command_key, digest)` first**: it returns an already saved Application and never dispatches a new effect. Its command_key is the original proposal's, not a new retry label, host run ID or guessed value. If it reports no existing execution or cannot be read, do not infer that nothing was accepted; continue the exact scoped lookup below and retain an unresolved state.

`execute_operations` can also recover its exact already admitted Application, but it is an execution entrypoint and must not be called as discovery when admission is unproved. Read/replay needs no new action consent; reuse the original exact choice. `queued` proves durable acceptance, while only `applied` with its per-object receipt/readback proves the provider effect. `unknown`, `partial` and `recovery_required` need reconciliation; none proves advertising benefit.

If the tool returns `operation_execution_outcome_unknown`, `ads_unavailable` or loses its response entirely, read `get_operations_work` with the exact project and plan_id and collection=applications, then read the returned ID with `get_operations_application`. Work returns paged summaries; follow the selected collection's next_offset when needed, and use existing plan/Application readers for full details. An unfiltered first page cannot prove no matching Application exists. Unrelated fact retry reads are optional and need their own bounded limit/offset; current native source jobs use list_daygrain_jobs/get_daygrain_job. If no matching Application is visible after the exact scoped read, the reader fails, or access is lost, report that verification is pending or forbidden; do not infer that nothing was accepted. Do not create a replacement plan, change command identity or blindly repeat execution. Reuse the user's existing choice for that exact plan; a recovered read requires no new consent.

For example, after consenting to one exact negative-keyword change the user sees a timeout: say “The execution response was lost; I will check the same plan.” A recovered `queued` means “Accepted, awaiting execution”; a proven `applied` means “The change is confirmed”; an unavailable read means “The state is still unknown.” Preserve the original references and next read in Work using [durable continuation](durable-continuation.md), with exact readback before claiming it is saved. On “What happened to that cleanup?” read those same references rather than propose the change again. A measurement still waiting for its frozen window is normal and does not block recovery acceptance; evaluate advertising outcomes later.

## Create a campaign from a domain

Fetch a bounded landing document and author a useful draft from its evidence. Missing confirmed geography may be a clearly labelled assumption for a PAUSED draft; budget, horizon and business-result targets are conditions for paid launch. Do not require a preliminary questionnaire before supported draft work.

Use the exact `final_url` exposed by the pinned landing manifest as copy.url. The current `creative_landing_changed` error identifies `reason=ad_destination_differs_from_retained_landing`, the URL field and safe expected final_url; it does not prove the page text changed. URI origin/default-port/root normalization is bounded; path, query and fragment retain their selected identity. Read the pinned manifest and correct the mismatched input only for the intended same destination. A different destination needs its own exact source and visible chosen material; a new capture is useful only when that evidence is needed.

In each creative's `evidence_ids`, use retained evidence object IDs accepted by the exact schema, such as the pinned `landing_source.artifact_id`; D7 span references belong only in `landing_source.evidence_refs`. Do not put span references or an Analysis publication ID into the legacy evidence-object list. A modern `analysis_basis` remains separate. For `evidence_not_found`, correct the source locator from the retained manifest; changing permissions or recapturing the same page cannot repair a wrong object ID.

Use `creator_account` native scope and a current compatible analysis basis. Create only the graph declared by the operation schema, in PAUSED state. If the creator schema cannot include negatives, make their separate exact group change visible after creation/readback; do not claim they were included. Read exact new IDs and graph state. Creation, moderation and finite paid launch each need their own explicit choice in chat and exact operation. Configuration readiness and a preview do not prove an applied effect; the user's choice does not prove provider readback.

Follow [the complete launch recipe](campaign-launch.md) for offer → supported SEARCH material → actual PAUSED creation/readback → separate moderation and finite launch → saved observation. Native `create_campaign`, including PAUSED, requires the catalog's seven-day finite money policy and actual VAT/funding/reserve inputs; absent prerequisites leave useful saved material, not an invented Plan.
