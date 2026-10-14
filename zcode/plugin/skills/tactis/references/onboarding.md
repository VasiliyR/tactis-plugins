# First useful result and measurement check

Use for «С чего начать?», a newly connected client, or «Можно ли доверять этим конверсиям?». Finish with one useful finding/material, an explicit measurement boundary and one next step. Reuse existing selections and evidence; onboarding does not require a full audit or a second OAuth consent.

| Stage | Tools and input source | Result / missing branch |
| --- | --- | --- |
| Choose client/account | [Shared session entry](session-entry.md); reuse its resolved scope and brief | Current selected account, own access, confirmed context and relevant Work. |
| Resume | Exact `get_work_session` from brief/known locator; full current continuation only for its work | Known offer, constraints, event choice and pending result are restored instead of requested again. See [continuation](durable-continuation.md). |
| Check access and data | `get_account_read_grant`; brief `source_publications`; `get_current_configuration` / `get_current_daygrain` when the exact locator/readiness is missing | Distinguish connection, read grant, available publication, pending capture and usable coverage. Brief captured_at/through/state describe the publication, not verified business measurement. |
| Check selected event | Configuration's exact campaign counter/goal bindings; `get_audience_sources` for bounded goal definitions; `get_business_context` only for truncated/needed confirmed context | Exact counter+goal, technical meaning, attribution and business correspondence. Different campaign goals are separate denominators. |
| First comparison | `get_campaign_metrics` with the **Daygrain** ID and closed window; `get_daygrain_manifest(include_coverage=true)` only for the relevant gap | Covered spend/traffic/event result with dates, units, VAT and limits. Follow next_offset; a bounded page is not the whole client. |
| Save and return | `record_work_session` → exact `get_work_session` | Compact result, exact sources, event meaning/unknowns and next step; [shared gates](invariants.md) apply. |

Read only the sources the user's first question needs. A ready current publication avoids capture; if absent, use the already authorized `capture_configuration` / `capture_daygrain` job path in [foundation reads](foundation-reads.md), retaining exact command identity and returned due time. A pending job allows a useful offer/text result. No connection or permission means the supported cabinet connection/access step, not agent-side credentials or grant changes.

## Measurement checklist

For a requested measurement check, return a short table **check → passed / needs_attention / unknown → evidence → consequence** using the checks below. For another first question, use only the checks needed for its result; a newly connected client does not by itself require the full table.

1. **Source and scope:** the campaign, linked counter and selected goal match the actual decision; no first-goal substitution.
2. **Event definition:** read conditions/steps/status. A phone, button or form-start event remains technical unless completed inquiry/qualification/payment linkage is established. Ask the one business question needed, for example «Эта цель фиксирует отправку заявки или только нажатие кнопки?».
3. **Delivery and coverage:** required dates/entities/event family are covered; distinguish known zero, missing, suppression/sampling and pending data. Source existence does not prove tracking works end to end.
4. **Comparison:** completed compatible windows, lag, units/VAT, timezone and attribution; Direct AUTO clicks and Metrika LASTSIGN events do not form one inferred conversion rate.
5. **Business outcome:** CRM source/mapping/payment evidence is available for the proposed sales/economics claim, or that claim remains unknown. Absent CRM does not block useful spend/traffic work.

Do not promise a tag audit, browser form submission, CRM SLA or bank-settled revenue from these readers. A relevant missing proof becomes one concrete verification instruction. A direct explicit new business definition uses `propose_context_bundle` and `apply_context_bundle` with that statement as the applicable choice, then exact context readback without another save question; [intake](mvp-workflow.md#intake-and-goals) preserves unspecified facts and distinguishes replacement. A stored attributed answer in Work alone has not applied business context, and inferred business meaning remains uncertain.

Finish now with the supported result: a covered change/limitation, a grounded first text, or a specific measurement instruction. Save the complete small material and its next check, then read it back. State what is useful today and what still limits the intended business judgement; installation, source readiness and a successful read have distinct statuses.

For project goals and their numeric interpretation, use [project goals](project-goals.md). The structured project model takes precedence over untyped legacy KPI keys; preserve exact historical context.
