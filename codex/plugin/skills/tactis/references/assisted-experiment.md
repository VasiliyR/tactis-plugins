# Prospective assisted comparison

Use only when the user wants a prospective controlled comparison and has a real external unique-user allocation mechanism plus binary-user observations. Ordinary [change cards and native pre/post reviews](experiments-workflow.md) are simpler supported results. These tools save a design and conditional statistics; they neither allocate provider traffic nor create/launch campaigns.

## Preparation and exact readback

1. Recover offer, original question, event definition, account and relevant Work. From current configuration read the **existing** control/treatment campaign IDs; each arm has one to ten distinct IDs and the arms are disjoint. New imaginary campaign IDs cannot create arms. If a campaign must first be made, complete that independent [PAUSED Creator path](campaign-launch.md) under its authority. Existing campaigns still do not prove random allocation.
2. Establish the real allocator: assignment by `unique_user`, equal treatment share `0.5`, stable unit identity, no cross-arm units and one binary converted unit per exposed unit. This release has only `assisted_randomized_parallel`. Different allocation units/shares, repeated event counts, sequential creative rotation and ad-level totals do not fit it; save the useful design with that gap rather than changing the schema.
3. Choose a future aware start, fixed one-to-ninety-day horizon, lag, exact counter/goal/attribution, primary event/business meaning, grounded baseline probability and minimum detectable **absolute probability difference**. Baseline+MDE must stay below one. The contract fixes alpha `0.05`, power `0.8`, and `fixed_horizon_single_final_look`; include meaningful guardrails and a concurrent-changes policy. Unknown assumptions remain unresolved, not universal defaults.
4. Call `prepare_assisted_experiment` with the current complete schema and one stable command_key. Save returned `id`/`fingerprint` and planning units per arm, then `get_assisted_experiment(project_id, experiment_id)` to verify the exact design. The planning approximation is not guaranteed achieved power. State `awaiting_external_allocation`, `provider_allocation_verified=false`, `launch_authorized=false`; preserving a Plan is not proof that allocation started.

### Synthetic shape example

All identifiers and assumptions below belong to an illustrative fixture, not a client or a reusable payload. The fixture must actually contain both campaigns; production substitutes IDs from its own inventory and grounded assumptions. Dates must remain future at actual preparation.

```json
{
  "project_id": "example-project", "account_id": "example-account",
  "command_key": "example-prospective-check-1",
  "hypothesis": "Clearer inquiry wording changes the share of users completing the form",
  "arms": [
    {"name": "control", "campaign_ids": ["101001"], "description": "Existing control offer"},
    {"name": "treatment", "campaign_ids": ["101002"], "description": "Existing treatment offer"}
  ],
  "design": "assisted_randomized_parallel", "allocation_unit": "unique_user",
  "treatment_share": 0.5,
  "assignment_description": "External system assigns each distinct user once with equal probability",
  "primary_event_definition": "At least one completed form is one binary event per assigned user",
  "counter_id": "201001", "goal_id": "301001", "attribution": "LASTSIGN",
  "business_meaning": "technical_event",
  "business_meaning_evidence": "Form completion only; qualification and payment remain unknown",
  "start_at": "2027-01-02T00:00:00+03:00", "end_at": "2027-01-16T00:00:00+03:00",
  "lag_days": 3, "baseline_probability": 0.1, "minimum_detectable_difference": 0.02,
  "alpha": 0.05, "power": 0.8,
  "stopping_rule": "fixed_horizon_single_final_look",
  "guardrails": ["Preserve the agreed spend and useful inquiry constraints"],
  "concurrent_changes_policy": "Keep other offer and targeting changes fixed; document any departure"
}
```

Native IDs are decimal strings on MCP wire, including nested arms; the backend validates native integer identities. Do not copy the fixture's probabilities, lag or spend rule into a client's design.

## Outcome input and interpretation

After the saved end plus lag, obtain the actual allocation record and actual source record from the authorized external system. `record_assisted_experiment_outcome` needs: project/experiment IDs; the returned **plan_fingerprint**; exact `allocation_record` and `source_record` plus their `*_sha256`; the saved start/end/counter/goal/attribution; actual observed_through; and each arm's `unique_units`/`converted_units`. Converted units cannot exceed units. The records are bounded text (10–4000 characters), not raw user identities. Hash exact retained record bytes with the agreed UTF-8 representation using a real hashing tool; never invent hex strings or treat a description of hashing as a receipt. A hash protects identity, not truth or provider provenance.

Record `allocation_checked`, `no_cross_arm_units`, `one_binary_event_per_unit`, `complete_coverage`, `guardrails_passed` and `concurrent_changes_absent` only from actual external checks. These booleans are **external attestations**; the service does not independently verify the allocator or source, even when all are true. Unknown/failed checks stay false with specific limitations. A wrong scope/fingerprint requires correcting the actual locator; immature data means wait. Do not manufacture maturity, sample or a re-randomization.

One final evidence look is admitted. Exact same evidence recovers that result; changed evidence after final publication is not a retry or a way to improve significance. Read `get_assisted_experiment` again and inspect the saved outcome, sample/sufficiency reasons, SRM diagnostic and limits before explaining it. `inconclusive` is useful; `conditional_estimate` still has `causal_claim=false` and `evidence_status=external_attestation_unverified`. Do not call this provider-verified A/B, a proven winner or causal business uplift. Save `experiment_review` with exact readable locators and the original criterion; use typed refs only when exposed. Any new Ads action follows its own [shared action gates](invariants.md).
