# Audience: understand, version, activate and return

Use [foundation reads](foundation-reads.md) and [durable continuation](durable-continuation.md). Audience turns existing behavioural conditions into a saved choice for an offer. Behavioural-condition analysis supports understanding sources, comparing choices and checking inclusions/exclusions. [Real segment versions and activation](platform-workflow.md#9-real-audience-segments-and-activation) add private CSV/Lifecycle selection and exact Yandex Audience create/replace with explicit consent/readback. Segment activation does not itself attach Direct targeting or suspend ads; use a separate supported provider operation.

## Toolbox by stage

| Stage / result | Use these tools | Boundary |
| --- | --- | --- |
| Restore the offer and selected condition | `get_project_brief`, exact `get_work_session` | Reuse prior text/rule; [continuation](durable-continuation.md) |
| Explain lists and actual consumers | `get_current_configuration`, `get_configuration_manifest`, `get_configuration_retargeting_lists`, `get_configuration_campaign` | Pin one configuration and page the needed families; a list name does not define behaviour |
| Check the selected goal meaning | `get_audience_sources` with its exact linked counter/goal scope | Definition/availability is distinct from business result and measurement eligibility |
| Revisit comparable group observations | `get_campaign_dossier(family=...)` pages; omit family only when metadata is needed | Group evidence does not prove audience CPA or random allocation |
| Preserve choice and hand to Creative/Ads | `record_work_session` → committed saved receipt | Full chosen rules/windows/offer, limits and next step; [shared gates](invariants.md). Actual segment activation uses the separate exact command/digest route; Direct targeting needs its own supported operation |

## Start from the client's existing decision

Read the selected project/account brief and exact prior Work/material locators. Reuse the offer, landing page, conversion meaning and constraints already supplied. Recommend the behaviour/window/message from these grounds using [the shared recommendation rule](onboarding.md#own-the-recommendation-and-the-next-step); ask only for a missing decision that changes it, not another complete brief. Keep a task-linked intermediate result pending with its actual `task_id` and `task_resolution="keep_pending"`.

Typical related requests:

- Understand inherited lists and which behaviour they describe.
- Compare two or three existing conditions for an existing offer.
- Include interest and exclude one selected event within explicit windows.
- Explain reuse across selected groups and where other criteria widen reach.
- Pass the chosen audience/offer to Creative/Ads without repeating context.
- Return after rules, offer, availability or group observations change.

## Understand the source before naming the people

Read every needed page of `get_configuration_retargeting_lists` and `get_configuration_campaign` (campaign, ad_groups, keywords, ads, audience_targets; bid_modifiers if claiming a complete consumer map). Pin the configuration publication/fingerprint, coverage and observed time. Old Unified complete/empty coverage may come from a skipped reader: only a proven read receipt supports absence. Source code or package version is not fresh evidence.

Read native Rules, ExternalIds, Type, IsAvailable, Scope and group compatibility. Do not infer behaviour from a list name. Goal/segment IDs are not interchangeable. A goal's MembershipLifeSpan describes that event's window; Metrika/Audiences segment windows require their own definition. State each goal window independently. No selected event in that window does not mean never a customer or purchaser.

Use `get_audience_sources` from the actual installed catalog for bounded selected-goal definition evidence: exact current configuration publication/fingerprint, account, proven campaign, currently selected linked counter and one to ten distinct goal IDs. It may show name/type/status/conditions/steps/depth and missing definition fields. The schema and current source guard determine availability. If this tool is absent or the source cannot be proved, retain exact confirmed goal meaning already present in context with its provenance, or record the missing definition prerequisite. Continue through the existing current-counter connection rather than collecting a new scope.

Read status `available` means the exact definition was read, not that it is complete enough for interpretation, eligible for a Direct list or selected for measurement. Counter-level failure leaves selected goals unknown. Goal 404 after a proven counter is missing; 403, transient errors and absent fields remain unknown. A partial response is not an empty audience. A shared 20-second definition-read deadline preserves completed items and labels remaining IDs unknown/deadline_exceeded with complete=false; it does not retry or turn an unproved counter into known goals. Source-time/fingerprint is evidence metadata, not a fabricated stored publication ID or typed ref.

Targeting and measurement eligibility differ: a retarget-only interest definition can be useful to understand intent while being ineligible as the measurement goal. Definition reading never relaxes the existing exact-goal proof. Direct IsAvailable/Scope/compatibility still governs list applicability. A technical form/click goal is not a qualified lead or paid sale without matching evidence.

## Choose for the offer and check exclusions

Return a small comparison of candidate conditions: source/confirmed meaning, inclusion and exclusion with windows, actual availability, existing groups, offer match and the remaining uncertainty. Explain why the chosen behaviour fits the offer; rank by that rationale, not invented audience size or future CPA. For example, a tariff-view event and a form-start event can imply different intent; their business meaning must be confirmed before that comparison.

For an interest-without-selected-conversion preparation, require:

- A positive interest rule AND a NONE rule for the selected conversion inside the same existing RETARGETING list. State the Rules exactly; ALL/ANY/NONE within a set and AND between sets have different meanings.
- IsAvailable=YES, applicable Scope and actual group compatibility; otherwise mark it as a preparation candidate with a concrete prerequisite.
- A separate existing Unified NETWORK group with an appropriate existing ad/offer/landing page and no alternative audience conditions, keywords/autotargeting or offer-retargeting widening the intended reach. In networks, other criteria may combine through OR; a NONE inside one condition does not exclude conversions from all group impressions.
- A known campaign/group state. ON under stopped parent delivery is not serving; no delivery/budget change follows from this choice.

When comparing reuse in several selected groups, map group → list → Rules/offer and state the examined scope. A shared list may also be used in bid modifiers and other campaigns. Do not call it a complete impact map or propose a safe global list edit without all relevant consumers. This analysis updates the saved decision. An actual segment replacement requires the separate prepared activation and current exact provider fingerprint. An unavailable unused list does not prove wasted budget.

A useful result can be: chosen preparation candidate, exact reason it cannot be applied, an existing material/brief for the offer, and the smallest next prerequisite. Do not fabricate an available replacement list/group or claim a connection. Absence of an applicable action does not prevent an independent Creative text or another supported Ads task from proceeding in its own scope.

## Save, return and compare at the supported level

Save ordinary Work with the choice, bounded alternatives, confirmed versus assumed source meaning, exact IDs/Rules/windows/offer/material, real evidence locators/fingerprints/time/coverage, unavailable action, next prerequisite and revisit event. Retain the actual returned Work ID from its committed receipt; local labels are meaningful only inside that Work. Do not create a new Audience schema or numeric assessment just to save the decision.

On return, read the prior Work first and current relevant configuration/definitions only as permitted. If source definition, Rules, offer or access changed, preserve old evidence as historical and save a revised choice linked to it. Do not silently carry an old exclusion forward. With unknown fields keep the usable portion and state the exact missing input.

For weekly comparison, use available dossier `ad_group_performance` facts only when goal/attribution, dates, delivery state and coverage are compatible. Call them group observations; overlapping conditions and different offers are confounders. Campaign-only metrics supply context, not audience CPA. Unknown size, suppressed conversions or insufficient denominators remain unknown. If delivery stayed stopped or the period is not mature, explain waiting. No pre/post comparison proves causal audience effect.

Return may end with retain the choice, prepare another existing condition/offer, ask for one unresolved definition or hand an observed issue to Ads/Experiments. A planned revisit is not an installed schedule; the closed host does not perform semantic review.

## Cross-product transition X1: Audience → Creative → Ads

Input already received: exact project/account, the existing offer/landing/material locator, constraints and any chosen goal/interest meaning from the same chat or prior Work. Read that material instead of asking the user to rewrite it.

Output for Creative is a saved audience package: selected list ID and exact known source IDs/meaning; positive/NONE rules and independent windows; offer/CTA and supplied material text or exact material locator; known limitations, selection rationale and what remains unconfirmed. Include the actual Work ID once saved, with original evidence locators. Creative can prepare texts for this choice; the handoff does not create an audience action.

Output for Ads adds selected campaign/group IDs if proven, scope/compatibility/coverage and the clear state **prepared audience choice; segment/provider targeting state separately verified**. Ads reads the chosen Creative text and existing rights/catalog; it may prepare an independent supported draft/plan. It must not pretend the audience was attached or transform the preparation into delivery consent. Experiments receives the saved intent/criteria and actual application only if one exists.

Missing transition: if goal meaning or group is unknown, send the known offer and limited audience hypothesis to Creative with that limitation; Ads receives the exact prerequisite, without fake plan/Application. Return in a new chat reads the original Work/material and newer real evidence, resumes the pending part and preserves independent completed material. Never invent stored IDs, effect, maturity or task completion.
