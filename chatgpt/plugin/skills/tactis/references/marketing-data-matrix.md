# Compare connected marketing data

The manifest may pool repeated column metadata in `column_contexts`. Expand each column's `context_ref` from that map, then apply its inline fields as overrides; `unit` stays explicit. This compact wire representation preserves source, calendar, cohort and formula evidence. Unknown context references are invalid.

Use this procedure when the question connects advertising, site events and CRM or compares their measurements. Reuse [session entry](session-entry.md), confirmed business definitions and [foundation reads](foundation-reads.md). An ordinary question about one available source can use its existing reader directly.

## Pin the input and build the matrix

Discover actual retained sources through the connector catalog and the appropriate owner readers. Choose exact publications before capture: Daygrain has its own publication ID and partition manifest fingerprint; CRM source, integrations, confirmed CSV and Marketing import have different locators and meanings. A connection, pending collection job or metric catalogue entry is not a completed input. Use the installed tool contract for the exact supported source kinds and fingerprint field; do not relabel a CRM publication or substitute an Analysis ID for Daygrain.

| Capture input | Exact reader / fingerprint |
| --- | --- |
| `daygrain_publication_id` + `daygrain_fingerprint` | `get_daygrain_manifest`: `id` + `partition_manifest_fingerprint` |
| `sources.kind="crm_import"` | The selected `get_crm_publications` confirmed CSV: `id` + `digest` |
| `sources.kind="crm_source"` | `get_crm_source_publication`: `id` + public `digest` |
| `sources.kind="integration_publication"` | `get_source_publication`: `id` + `fingerprint` |
| `sources.kind="marketing_publication"` | `get_marketing_publication` with `kind="import"`: `id` + `fingerprint` |

Each source selection also carries its actual `account_id` or null. The completed matrix retains additional full-source integrity fingerprints; do not substitute those for the original owner's capture fingerprint. Preserve the exact request for replay.

Call `capture_marketing_data_matrix` with the exact project, explicit scope, requested completed window/timezone, applicable account/source binding, exact Daygrain ID/fingerprint and selected source publications/fingerprints. Use an explicit counter/goal when the question concerns that event. Never choose the first goal merely to fill the matrix. Project-only source summaries do not require Direct; account/campaign facts retain their actual account. Preserve the same command key and all inputs to recover a lost response. Capture computes from retained facts; it does not collect new provider data or change advertising.

Use the manifest returned by successful `capture_marketing_data_matrix`: it explains metric definitions, exact input references, source summaries, scope and limitations, and confirms the committed result. Read `get_marketing_data_matrix` when that manifest is missing or when returning to an existing matrix. For campaign rows, call `get_marketing_data_matrix_rows` with a small initial limit and follow every returned `next_offset` for the requested scope. Pages can be smaller than the requested limit because whole rows have a response budget. Keep the exact matrix ID and fingerprint across pages; a first page does not represent the whole account. A summary with no campaign rows can still answer a project/source question.

## Interpret each value in its own scope

Use owner-provided cells and formulas. Preserve their state, units, event definition, attribution, tax/currency basis, coverage, input references and contributing source as-of. The matrix capture time is computation time; old source receipts do not become fresh from a new matrix. Missing, partial, incompatible and observed zero differ. A zero denominator leaves an undefined ratio. Read an unknown cell's reason before proposing a change; its next prerequisite is often more useful than a performance verdict.

An omitted cell `maturity` inherits the manifest/page `maturity_default`, explicitly `unknown`. Formulas use the manifest's global registry `formula_version` unless a column supplies its own override.

Direct AUTO and Metrika LASTSIGN remain separate observations. Direct CTR/CPC/CPM use their own compatible traffic/cost inputs. An exact Metrika goal-per-visit ratio requires the same counter, campaign, window and attribution; it counts goal events per visit and can exceed one. Visits/clicks is a diagnostic relationship, not proof of unique people reaching the site or a measured loss caused by the landing page. Several goals can overlap and must not be summed into total leads.

CRM qualified, won, CRM-marked paid and cash payment remain different meanings. A creation/current-status cohort is not orders paid during the requested period. Native CRM and imports without proven native campaign lineage remain source/account/project summaries. Never allocate their sales or revenue across campaigns by spend, clicks or lead shares. Confirmed CSV campaign observations require the owner's exact historical binding and declared cohort proof; a matching number or current remapping cannot supply it. A blocked cohort cost or cross-source money ratio stays unavailable. Missing taxes, refunds, costs or acquisition evidence cannot become ROAS, CAC, ROI or profit through a spreadsheet formula.

Do not sum different source summaries or correction versions without proof that their populations do not overlap. A source's full acquisition coverage does not establish correct business event meaning, mature conversions, person-level attribution or causal uplift. Keep the supported observations and identify the exact missing prerequisite for a stronger decision.

## Save and return

For a relevant [backend signal](project-signals.md), read its original observation and keep that exact signal `evidence_ref` alongside the matrix reference in Work. Record the supported `signal_responses` disposition and reason; the matrix cannot replace the observation or the response required to close its review task. A saved response and delivery acknowledgement do not repair the source condition. Matrix capture introduces no signal detector or background decision.

Save the substantive finding through ordinary Work with `platform_refs.kind="marketing_data_matrix"`, the exact matrix ID, its actual account or null and manifest fingerprint. Use the same exact reference in the applicable new/revised continuation.mode="delta" entry and retain the committed saved receipt through [durable continuation](durable-continuation.md). Matrix-only work does not require inventing an Analysis or versioned external assessment. New Work rechecks current input authority; a historical matrix read does not establish current dependency state.

On return, read the saved Work and exact matrix first. Preserve the original historical conclusion; changed source data needs a new publication and a new comparison. A stale/denied source cannot be bypassed by copying old numbers into a new verified Work. Use [visual analysis](../../tactis-visual-analysis/SKILL.md) for an informative table/chart with the same cells and limitations. For a requested matrix-only document use a grounded authored HTML material and exact material readback; the fixed Analysis report still requires its actual compatible A1 basis.
