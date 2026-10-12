# Advertising got worse: check the loss and choose what to do first

Use for «Результат рекламы ухудшился: что проверить и что делать первым?», fewer events, or rising acquisition cost. Return a diagnosis and up to three priorities in chat. [Foundation reads](foundation-reads.md) owns collection/paging; [durable continuation](durable-continuation.md) owns rights, exact references and save/readback/return.

Choose the matching row of [ten ordinary symptoms](optimization-recipes.md) when a specific CPA, CTR, SEARCH/РСЯ, quality or budget question needs a drill-down. The five stages below remain the short diagnosis spine; do not run every symptom or a full audit. Shared decision/unknown gates are in [invariants](invariants.md).

## 1. Recover the scope and name the symptom

Resolve client context through [session entry](session-entry.md), reusing known scope, selected event, prior decision and restrictions. Clarify only what changes the diagnosis: does “fewer leads” mean a technical event or qualified inquiries? Without CRM, assess advertising traffic/spend and available events, naming the business-outcome gap.

Name campaign scope and periods. Use the user's comparable periods; otherwise explain the mismatch and give the supported trend. For an unspecified weekly decline, use the last two completed Monday–Sunday Moscow weeks available in the publication, respecting source lag.

## 2. Compare the available facts before diagnosing a cause

Resolve a missing `source_binding_id` with `get_account_read_grant`. Pin `get_current_daygrain(project_id, account_id, source_binding_id)`. Read `get_campaign_metrics` with that **Daygrain** `publication_id`, `project_id`, `start`, `end`, `source="direct"`, `family="campaign_performance"`, `aggregation="calendar_week"`. Start with a small `limit`; follow `next_offset` for the intended scope. Names are already returned. Retain row dates/coverage; clipped or incomplete weeks are not equal comparison windows. For other exact equal windows, use `aggregation="total"` separately.

Read `source="metrika"`, `family="metrika_exact_goal"` for the relevant exact `counter_id`/`goal_id`; visits use `metrika_counter_visits` with `counter_id` and no goal. Use actual campaign bindings. Different/overlapping goals cannot become total leads; Direct AUTO and Metrika LASTSIGN cannot supply an unproven cross-source CR/CPA. Retain currency/VAT, timezone, attribution and event meaning.

For null/partial metrics use that publication's `get_daygrain_manifest(include_coverage=true, start=..., end=...)` and relevant `get_daygrain_receipts(covered=false, family=...)`. Name the missing family/window and next check; pending collection follows its job/due-time route. Keep covered traffic/spend useful. Verified zero delivery prompts configuration checks; zero events with traffic prompts tracking/event and landing checks. Neither establishes a cause.

## 3. Locate the main known deterioration

Show previous/current spend, clicks, selected events, changes and unknowns. Rank compatible additive negative event contributors separately from positive offsets. Label subtotals by their members; missing campaigns remain unknown. Without a meaningful goal, locate the known traffic/spend change rather than claim poor leads.

For needed economics reuse `get_analysis_manifest`, its comparison/`comparison_explanations`, and `list_analysis_campaigns`. Only if needed, `capture_analysis` uses exact `daygrain_publication_id`, `period_start`, `period_end`, chosen `conversion_source` and a compatible `baseline_analysis_publication_id` when available. Preserve unavailable/incompatible metrics. Basic traffic/spend needs no analysis; missing revenue cannot become profit. [Ads contribution arithmetic](ads-workflow.md#diagnose-and-choose-a-priority) supports a descriptive decomposition, not causation.

## 4. Check the selected explanation, then choose a result

Inspect the main known loss first:

| Observed symptom | Addressed check and attainable result |
| --- | --- |
| Fewer impressions/clicks or verified zero delivery | `get_current_configuration` → `get_configuration_campaign(family="campaign")` settings/status; relevant saved `get_operations_plan`/`get_operations_application`. Distinguish captured settings from current delivery. Lower traffic alone does not justify increasing budget. |
| Traffic remains, selected event deteriorates | Unknown event meaning → `get_audience_sources`. Relevant query/device/placement question → reuse dossier, or `capture_dossiers` from matching analysis → final `get_dossier_manifest` → `get_campaign_dossier` → needed `get_dossier_family` pages (`search_query`, `device`, `placement`). Pending job is not evidence. Suspected ad/landing mismatch → exact configuration and `get_landing_page(kinds=["title","heading","text"])`. Absent events alone do not justify negatives. |
| Complaint concerns qualified inquiries/paid sales | Retain the advertising diagnosis; pass the unresolved qualification/payment question and exact evidence to [Sales](sales-workflow.md). Missing CRM does not block the covered advertising result. |

Return up to three priorities: **object → evidence → interpretation/unknown → next check or exact material → revisit condition**. Put the supported loss relevant to the user's objective first, without universal CPA/minus/budget thresholds. Deliver a grounded draft, named tracking/configuration check, or no-action with revisit condition. Actual change preparation follows [current actions](current-actions.md#change-an-existing-campaign) and its catalog/freeze/choice/execution/readback procedure.

## 5. Save the useful diagnosis and return to it

Use `record_work_session(kind="assessment")`, or `no_action` for an explicit wait. Summarize the diagnosis rather than copy the whole chat: retain periods/scope, known loss and priorities in `summary`, uncertainty in `limitations`, and the first check in `next_step`. Follow the installed schema limits (currently `summary` ≤4,000 characters and `next_step` ≤2,000). `foundation_refs` carry actual supported `kind`, `id`, `account_id`, `fingerprint`; Analysis IDs never enter legacy `facts_ids`. Without analysis, omit optional `assessment`. Follow the linked continuation procedure for snapshot/CAS/unfinished tasks; read returned `get_work_session` before saying it is saved.

On return read the same Work and first check, then changed relevant source/plan/Application state. A saved recommendation is not an applied change or proven improvement.

**Synthetic example, not runtime evidence.** In two covered equal weeks with the same additive technical event, campaign A changes 30→15, B 20→15, C 10→15. The selected total changes −15; A contributes −15, B −5, C offsets +5. First inspect A's traffic/configuration and matching evidence. Say “A is the main known negative contributor; I will check its delivery and event evidence,” not “A caused fewer sales.” Save that check with the diagnosis; no budget or negative-keyword write follows from these counts alone.
