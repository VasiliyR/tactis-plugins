# Lifecycle selection, manual application and matched feedback

Use with the [Lifecycle workflow](lifecycle-workflow.md). Read prior exact Work first, reuse rule/material/context and ask one missing condition at a time. Prefer actual connected cohort/outcome publications when exposed; they need no manual table. In assisted fallback use the smallest existing report from the client's system, without a complex spreadsheet or personal exports. Supplied manual numbers remain business-reported.

## Connected publication feedback

Read actual `get_lifecycle_cohort` and `get_lifecycle_outcome` receipts under current project/account scope. Keep source publication IDs, immutable cohort ID/fingerprint, exact material/rule/as_of, buyer_mode, all-visible coverage and saved maturity window. Do not reconstruct identities or refresh a saved cohort by a new selection. New source capture and new outcome each receive their own actual ID.

`purchase_rule_count` is a gross full-paid recency count for the visible Sales funnel. A company-mode buyer is a company, not a contact. `observed_rule_buyer_count` on partial data is an observed subset selection, not necessarily a lower bound on the final rule result: missing fresh purchases can remove a currently observed member. Unknown refund/consent/channel/suppression leaves contact eligibility unknown even for complete purchase data. Do not subtract guessed exclusion totals or call this a recipient list.

For compatible complete outcomes backend fixes original denominator and matches unique repeat buyers; multiple new orders can exceed buyer count. Old baseline orders paid later and newcomers are excluded. Missing baseline orders, changed prior paid semantics, backdated new rows, identity/mapping drift or partial capture leave rate null with gaps; denied source/custody means observation unavailable. Preserve the original publication rather than patching its group. An immature observed share remains explicitly immature until a later source publication reaches saved `mature_at`; wall clock does not mature existing evidence.

CRM-reported gross paid share is useful observed feedback, not net paid, delivery rate, causal message effect or profit. Known complete zero repeat buyers is zero; empty denominator and missing data are null. Keep refunds/costs unknown and pass actual same-cohort scope/limits to Profit. Manual channel application remains separately reported and never changes frozen purchase denominator. The report checks below apply only to assisted fallback or separately reported communication eligibility/application.

## Check the selection without reconstructing customers

For a usable report, identify source and selected project/account, scenario Work/local rule version, selection date/timezone, category/window and count unit (unique buyers rather than orders or leads). Keep the client's non-personal group/report locator, snapshot cutoff and stated coverage. The client's system must link purchases to buyers and hold the original group. If a locator or snapshot capability is absent, name the limitation; do not generate a supposed source cohort ID yourself.

Use a reported base and successive remaining counts for the exclusions that the existing system can check. Each remaining count is evaluated on the previous remaining group. Check nonnegative integers and non-increasing counts; explain the removed count by subtraction. This verifies arithmetic, not membership or truth. Check refunds, later purchases, open orders/complaints, channel eligibility/opt-outs and recent-contact suppression; let the operator combine checks already present in a small report. Explicitly preserve any unverified exclusion. A larger step after an exclusion, a changed cutoff/unit/account or missing coverage prevents an exact reconciled result.

Independent criterion counts may overlap: do not subtract their sum from the base. Do not deduplicate customers yourself. Ask for one existing final AND-filter result or successive remaining counts, whichever the operator can obtain more easily. If only the final eligible count is available with a precise rule/source/date/coverage, it can be retained as reported; intermediate removals stay unknown. If eligibility cannot be checked at all, correct the condition and leave the size/selection unverified. A source-backed completed zero differs from a missing report.

When both next purchase and winback are prepared, verify non-overlap or the source's explicit priority/suppression. Do not add their counts as a portfolio total without a common unit/source/cutoff and proven disjointness. Prefer one material correction, such as explicitly changing an old-order filter to the last eligible purchase with no later order. Do not weaken opt-out or widen windows merely to increase counts.

**Conditional selection example.** For one shop and one cutoff, reported unique-buyer counts are:

| Case | Base | No later purchase | No open order/complaint | Channel eligible, opt-outs and recent-contact limit checked |
| --- | ---: | ---: | ---: | ---: |
| R1 next purchase | 120 | 90 | 80 | 60 |
| R2 winback | 75 | 65 | 55 | 40 |

Refund treatment was checked in the initial base, and the operator explicitly says all named final checks are included; do not assume this from the table header alone. Removals are 30/10/20 and 10/10/15. The result is reported60/40 as of the source cutoff, not Tactis-verified recipients. If the original rule admitted an old purchase despite a later one, produce the exact last-purchase correction and ask for a fresh final selection before contact. Save that correction and limitations alongside the exact unchanged material.

**Missing selection example.** «Всего120, повторно купили30, открытых заказов10, отписались20», with independent groups, does not prove60 eligible. Give the corrected last-purchase rule and a useful request: «Для той же даты примени исключения вместе и сообщи окончательное число пригодных покупателей; если отчёт уже показывает последовательные остатки, достаточно их. Имена и контакты не нужны». Keep unknown overlap/eligibility; do not replace unknown with zero or send to the presumed60.

## Keep manual application distinct

Before any manual contact, the operator checks fresh group membership, all exclusions, contact limits and the selected exact offer/copy/channel. For a follow-up repeat that check, including purchases since the first contact, and apply the saved stop conditions. If the system cannot suppress new purchasers or opt-outs now, the follow-up remains unready. A previous snapshot or an unchanged message is not permission to reuse yesterday's recipient list.

The user receives the complete package in this chat. Retain any actual client-reported campaign/job locator, selected message Work/version, date, attempted/delivered counts and failures if available. Record «Ты сообщил, что…» for reported selection or sending. Do not claim Tactis/provider delivery, use `execute_operations` for email, forge an Application, send another chat/email or mark a task complete from a prepared text. Reported attempts and reported delivery are different states. Unknown delivery is not failed or zero delivery.

## Observe repeat payments in the same source group

For an interpretable observation, the client's existing system must preserve frozen membership and match subsequent orders to its buyers. Retain the original group/rule/material locators and base date; the actual observation start/end/timezone, category or whole-basket definition, lag/cutoff, payment/refund treatment and source coverage. Ask for the smallest missing piece of an existing cohort report rather than all fields at once. A dynamic group today is not necessarily the original contacted group. The source report stays in the client system; no personal records are read here.

Separate:

- Unique eligible buyers in the original frozen group.
- Actual reported contact attempts and delivered messages, with their unit and cutoff.
- Unique buyers in that original group with a qualifying new paid purchase in the observation window.
- Number of orders, cancellations/returns, revenue and contribution only when separately available and defined. A refunded order does not qualify under a net-paid rule; agree how partial refunds are treated.

Calculate externally **repeat-buyer share = matched unique repeat buyers / unique buyers in the original eligible frozen group** when definitions/coverage are compatible. Payment before the observation window is not a new observed repeat. Do not divide a whole-group purchase numerator by a delivered subset unless the source supplies the numerator matched to that subset. A zero denominator makes the ratio unavailable, not zero/infinite. Orders can exceed buyers; a unique-buyer numerator exceeding its base is a data/unit error. Partial/unknown coverage or an unfinished business window prevents calling the observation complete/mature. Do not invent maturity from today's date or a made-up refund lag.

**Conditional outcome example.** At the stated completed window and coverage, the operator reports R1 eligible60, delivered58, unique new net-paid buyers12; R2 eligible40, delivered38, unique new net-paid buyers4. Repeat-buyer observations are12/60=20% and4/40=10%, labelled business-reported with their actual window/source. Delivery counts do not change these denominators. These groups differ by recency; their percentage difference is not an A/B winner, increment from messages, proof of loyalty or profit. Review the known material/source and propose one next action, e.g. preserve R1 as a trial and check R2 offer relevance before continuing, with the actual limitation and condition for return.

**Missing outcome example.** «После письма в магазине15 продаж» plus account totals does not identify repeat purchases in either group. Preserve the useful reported application, leave matched repeat buyers/rate unknown and ask «Есть ли в текущем отчёте новые оплаченные заказы именно исходной группы за это окно, с учётом возвратов?» If no matching capability exists, say that this outcome cannot yet be measured through this source. Do not backfill cohort counts from CRM totals or broaden into a new reader/CDP.

## Save the decision and continue

Follow [durable continuation](durable-continuation.md) for actual schemas/save/recovery; retain exact selection/material/prior Work and source locators, state, source/date/coverage, compact table/calculation, limitation and next result. Ordinary `assessment` Work is suitable without A1 or a continuation head; source report locators remain attributed text, not typed foundation evidence. Keep task-linked intermediate pending only when the current schema explicitly supports Platform keep_pending; otherwise save ordinary Work without `task_id` and retain its source task locator. Never infer task done from an observed count.

On return, read exact scenario and feedback Work, distinguish a new snapshot from a corrected old report, and change only the affected calculation/rule/material in a new Work with predecessor. If the same report is re-presented, do not add it as another batch. Keep the prior accepted text verbatim unless the user actually selects a revision. Carry real source/cost data into the same-model Creative/Profit X3 handoff under the main workflow; missing contribution is not profit, a draft offer is not budget approval. Stop/pending/unknown remain visible. This is an assisted observation and useful decision, not a verified channel operation or causal measurement.
