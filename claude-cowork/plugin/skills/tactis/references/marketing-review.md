# Marketing review: audit, rhythm and a decision report

Use the requested mode only: an audit, a repeatable review rhythm, or a report for an actual decision. An ordinary symptom uses [optimization recipes](optimization-recipes.md), not this full audit. Reuse frozen evidence through [foundation reads](foundation-reads.md), shared [invariants](invariants.md) and [durable continuation](durable-continuation.md).

## Audit with evidence rather than a magic score

Agree the authorized campaign scope, objective and completed observation window from existing context. First establish Daygrain/Analysis coverage with `get_current_daygrain`, `get_campaign_metrics`, `get_analysis_manifest` and needed `list_analysis_campaigns` pages. Reuse the matching Dossier; if missing, `capture_dossiers` from exact Analysis → `get_dossier_manifest` → `get_campaign_dossier` identifies available families. A full-account audit requires the needed complete inventory/pages; a selected campaign audit remains selected.

Use relevant `capture_candidates` only if no matching retained Candidate exists. Its `get_candidate_manifest` and `get_candidate_family` are mechanical hints over one campaign, not a pass certificate. Retain source fingerprints and family coverage with each finding. Inspect supported source rows/settings before deciding. No R8/R9 family is exposed in this runtime.

| Check | Evidence/tool route | Applicable decision |
| --- | --- | --- |
| Measurement and objective | Exact `get_audience_sources`, Daygrain row coverage/manifest/receipts, Analysis goal/comparison limits; CRM definition when required | Can this stated outcome be measured for this scope/window? |
| SEARCH intent and useful demand | Dossier search_query/query_observations plus current keywords; R1/R3/R5/R10/R11/D1 only as relevant hints | Grounded exclusions, preserved useful demand, missing matched group/material |
| РСЯ placements and devices | Dossier placement/device and exact event; R2/R6/R7 with coverage | A bounded exclusion/modifier check, or insufficient observation |
| Group structure and eligibility | Dossier ad_group_performance/ad_groups/structural_findings; R4/structure; scoped Configuration | Actual structure/eligibility gap versus mere absence of a candidate |
| Message and destination | Exact Configuration ads, creative findings, retained Landing spans/final URL | Unsupported claim, mismatched destination or complete grounded material; no ad-level uplift inference |
| Economics and business capacity | Analysis/economics/efficiency, compatible paid/cost aggregates and [Profit](profit-workflow.md) | A feasible paid-sale limit or explicit missing financial grounds |
| Changes awaiting a result | Exact `get_operations_plan`, `get_operations_application`, `get_native_measurement`/`get_native_outcome` when known | Applied/unknown state, still-immature observation, next meaningful check |

Output one row per actually applicable check: **object/check · passed/failed/unknown/not_applicable · evidence and coverage · severity/reason · next step**. Passed means a defined criterion was checked on sufficient evidence; failed means evidence contradicts that criterion. Unknown names the missing condition. Not_applicable names why this check does not concern this campaign/objective. An empty candidate list proves only no returned candidates in its declared coverage, not health. Preserve known zeros separately.

Use severity only to explain the user's next priority: a blocked agreed outcome, a demonstrated material mismatch, or an improvement hypothesis. Do not assign an arbitrary 0–100 score or imply quantified loss without the needed grounds. End with at most three ordered actions and one ready material/assignment. Save/read back the bounded scorecard and the first next step; larger evidence stays in its immutable sources.

## One daily, weekly and monthly rhythm

Give this one table adapted to the user's objective, business lag and current sources. A suggested rhythm is not an activated schedule. [Automation](automation-workflow.md) governs real subscriptions/host turns; closed-host capture does not make an external agent perform reasoning.

| Return | One useful task and tools | Enough evidence and output |
| --- | --- | --- |
| Daily exception check | Reuse latest `get_current_daygrain`/relevant metrics and exact pending Application/measurement; refresh/job readers only for an actual stale or due source | Fresh covered exception against the agreed constraint, or “no new usable observation”. Output one urgent check, no full daily audit; unfinished days and immature conversions remain provisional |
| Weekly priorities | Comparable completed windows → [diagnosis](performance-diagnosis.md); read changed Sales/source or outstanding assignment only when relevant | Up to three priorities, one completed/remaining assignment and its next result. Same event/cohort/lag is required; no universal seven-day maturity |
| Monthly economics and structure | [Profit](profit-workflow.md), scope-specific audit above, existing experiment decision/material reuse | Compatible mature contribution/paid comparison or named missing inputs; chosen budget/offer/structure priority and next observation condition, without reopening every old hypothesis |

Triggers can replace a calendar return: a source/job becomes complete, an exact application gets readback, the agreed maturity window ends, or business offer/capacity changes. Use actual trigger/time enums from the installed schema, never invent them to save a head. Unchanged sources can yield a useful pending-state return, not fabricated fresh findings. Proposed dates/owners remain proposed until actually agreed.

## Report for a decision

Start with the recipient's decision, reusing a known recipient/objective: “Что решаем — продолжить, исправить или перераспределить?” For an unspecified recipient, a compact working chat review is enough. Use already pinned evidence rather than recapturing sources to make a document.

Give **decision needed → measured facts and comparison → interpretation/alternatives → risks/unknown → proposed action and actual/proposed owner → next measurement**. Keep spend currency/VAT, Moscow/source timezone, goal/attribution, coverage and maturity beside the numbers. Use one [appropriate chart/table](../../tactis-visual-analysis/references/charts.md#data-matrix-for-all-sixteen-types) only when it helps the decision. A useful chat review does not require export.

**Synthetic weekly example:** “За две полные недели расходы 40→45 тыс. ₽ без НДС, технические события 20→15; оплаты неизвестны. Основной известный отрицательный вклад — кампания A, −6 событий, другие +1. Предлагаю первым проверить её изменившийся SEARCH-запрос/посадочную; это проверка гипотезы, не доказанная причина. Исполнитель — предлагаемый владелец рекламы; готовность — точный запрос, действующий текст/URL и решение сохранить/изменить. Следующий замер — согласованное зрелое окно после фактического изменения”. Substitute actual facts and known owner/conditions; the example does not imply authorization or causation.

Save relevant `record_work_session` first and retain its committed receipt. Only for a requested separate HTML/PDF report use `create_analysis_report` with actual saved `work_session_id`, exact `analysis_publication_id`, supported mode `overview|audit|launch|experiment` and bounded narrative. The saved Work must contain the schema-required analysis basis; a prose CRM/portfolio summary is not that basis. Launch/experiment require actual Application and compatible measurement/outcome fields. Read `get_client_report` for resulting status/artifact; do not claim a generated file from admission alone. Retain limitations in narrative and chat. A portfolio report without a matching supported Analysis is a chat/table deliverable or another explicitly available host export, not a fabricated Tactis report subject.

An explicit request for a public link uses the [saved HTML publication procedure](mvp-workflow.md#publish-a-saved-html-report), or the [client-report skill](../../tactis-client-report/SKILL.md). Reuse the exact existing report and chosen access policy, verify the publication and return its actual link/condition. Ordinary analysis and document creation do not automatically publish it; public availability does not prove message delivery.
