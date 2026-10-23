# Backend signals in the agent's work

Use this procedure at connected entry, return to saved work, before a material decision, or when a user-created signal review task is assigned. Monitoring, project-goal and automatic analytics observations share a read surface. Their exact source evidence and meanings remain with the original owners. The backend collects facts and evaluates existing rules; the external agent decides how the relevant observation affects the user's work.

## Read the signal that matters to the task

1. Reuse the selected project/account and the signals already relevant to this task. The ordinary MCP brief does not load attention or source heads; reading a signal does not require another brief. Preserve project-only work even when a primary advertiser exists.
2. Use `list_project_signals(project_id, account_id?, limit, offset)` for compact signal pages when needed; follow `next_offset` to find relevant items. `consistency="live_owner_heads"` means later pages can reflect changed heads, not a frozen audit. The list covers existing monitoring, project-goal and publication-triggered analytics observations, not every possible source defect. Its summaries do not replace exact reads.
3. Read `get_project_signal(project_id, signal_id)` for the selected immutable observation, its current status/locator and exact `evidence_ref`. Inspect `current`, `current_observation_id` and `attention_required`; if `details_truncated` is true, follow `observation_reader` for the complete owner observation. A returned `last_response` locates earlier saved Work; read that Work before reusing its conclusion. IDs are `monitoring:<observation_id>`, `project_goal:<observation_id>` and `analytics:<observation_id>`. Preserve the returned identifier; task IDs, source IDs and Work IDs are different locators.
4. Check the observation's actual scope, dates, event definition, coverage, maturity, thresholds and current relevance. Recheck the needed source or goal when a later observation, changed context or stale basis can alter the decision. An old signal remains exact-readable evidence of its original window; it does not prove the same condition still holds.

Read only the signals and supporting evidence that can change the requested result. A relevant limitation may change the recommendation, require a check or be explained in the answer. An unrelated signal does not redirect a focused request into a full audit. A zero count or successful connection does not prove data quality, measurement completeness or business success. Missing or partial facts do not become observed zero; a goal evaluation does not establish a causal effect or authorize a provider write.

## Save how the observation affected the decision

In the substantive `record_work_session`, add a `signal_responses` array. Each entry contains the exact `signal_id`, one `disposition` and a concrete `reason`:

| Disposition | Use when |
| --- | --- |
| `considered` | The evidence was assessed and the stated decision remains appropriate; explain why. |
| `investigate` | A relevant uncertainty needs a specific next check; name that check. |
| `deferred` | The review is complete but the next decision waits for a stated time or event. Explain that condition in `reason` and retain the next check in Work. |
| `not_applicable` | This observation does not apply to the user's selected task or current basis; explain the scope or evidence mismatch. |
| `decision_revised` | The signal changed the conclusion or next step; state what changed and why. |

For a deferred decision, give a concrete next check in Work `next_step` or the complete continuation's existing `revisit_at` / `revisit_event`; the server requires one of these. Use timezone-aware continuation dates and testable events, and name the signal's own condition in its `reason` when several signals have different next checks. Another chat recovers these existing Work fields. A response describes the agent's decision; it never marks the underlying data condition as repaired. Later source observations establish recovery or a changed goal state.

Also include the returned `evidence_ref` as an exact typed `platform_refs` entry: `monitoring_observation`, `project_goal_observation` or `analytics_observation` with its owner ID, account scope and fingerprint. A response alone does not replace this evidence or supply an assumed digest. One Work can respond to several signals with separate entries and exact references; `task_id` still identifies only one assigned task. Do not fabricate multiple task closures in one Work.

Use the normal current context/generation checks, command-key recovery, continuation delta/CAS and committed saved receipt from [shared invariants](invariants.md) and [durable continuation](durable-continuation.md). Automatically save a substantive finding, changed decision or next check. Routine successful persistence stays silent. If a save is rejected or its outcome unknown, explain that limitation and recover the same command before treating the reaction as durable. Earlier Work that has no response field remains historical evidence; do not rewrite it.

This synthetic Work shape illustrates three reactions and one assigned task. It is not an executed result; replace every example locator, fingerprint, scope and conclusion with the actual reads. Add the relevant continuation.mode="delta" when retaining the next check.

```json
{
  "project_id": "project_example",
  "command_key": "signal-review-example",
  "kind": "assessment",
  "summary": "The assigned monitoring review is complete; the goal decision awaits mature evidence.",
  "next_step": "Revisit the goal when its specified source evidence is available.",
  "task_id": "monitoring_review_example",
  "task_resolution": "complete",
  "signal_responses": [
    {
      "signal_id": "monitoring:observation_example",
      "disposition": "considered",
      "reason": "The exact observation was assessed for the selected task; its data limitation is retained in the conclusion."
    },
    {
      "signal_id": "project_goal:goal_observation_example",
      "disposition": "deferred",
      "reason": "Defer the goal decision until the owner publishes complete evidence for its window after the conversion lag."
    },
    {
      "signal_id": "analytics:analytics_observation_example",
      "disposition": "investigate",
      "reason": "The versioned rule reports a comparable spend change; investigate its cause and business meaning before changing advertising."
    }
  ],
  "platform_refs": [
    {
      "kind": "monitoring_observation",
      "id": "observation_example",
      "account_id": null,
      "fingerprint": "0000000000000000000000000000000000000000000000000000000000000000"
    },
    {
      "kind": "project_goal_observation",
      "id": "goal_observation_example",
      "account_id": null,
      "fingerprint": "0000000000000000000000000000000000000000000000000000000000000000"
    },
    {
      "kind": "analytics_observation",
      "id": "analytics_observation_example",
      "account_id": null,
      "fingerprint": "0000000000000000000000000000000000000000000000000000000000000000"
    }
  ]
}
```

## Complete an assigned review

The signal's `review` shows the work state separately from the metric: `awaiting_agent` means a visible task is pending and no saved response exists; it does not imply a model has run. `in_progress` retains a saved intermediate reaction while the task remains pending. `closed_without_review` means someone closed the task but no verified saved reaction exists; do not report an analysis as performed. Read the observation and save the actual decision before continuing. `reviewed` links that saved decision through `result_work_session_id`; read the exact Work and next step. `cancelled` and `no_task` do not promise a future automatic review. A reviewed signal may still require attention because the underlying metric has not recovered. A host that has not run leaves the task waiting; the next authorized real turn can read the task, review current facts and save its actual result.

For `monitoring_review`, match `monitoring:<task reference_id>` and its exact monitoring observation. For `project_goal_review`, match `project_goal:<task reference_id>` and its exact goal observation. For `analytics_review`, match `analytics:<task reference_id>` and its exact immutable analytics observation; a matrix reference alone cannot close this review. Read the actual task rather than assuming a list item is assigned to you. Closing an automatic review requires a matching `signal_responses` entry and its exact `platform_refs` evidence in the task-linked Work.

Use `task_resolution="complete"` only after delivering the task's requested review. A completed review may reasonably defer a later business decision if its response gives the next check. An unfinished requested result uses `task_resolution="keep_pending"` and does not satisfy delivery acknowledgement. [Proactive delivery](proactive-delivery.md) adds the current host policy, actual claim/lease, complete saved result and exact acknowledgement checks. A pending task or enabled policy does not create a host scheduler or a hidden LLM turn.

The agent can revise a recommendation, prepare a supported check or explain why the signal does not affect this task. Any external action still follows the existing exact plan, applicable human choice, permission and readback procedure. Deterministic analytics workers evaluate versioned numerical rules on admitted publications; they do not run a hidden marketing model or execute advertising changes.

## Automatic analytics and several signals

Automatic observations contain the exact rule/version, thresholds, source fingerprints, windows, sufficiency, assumptions and reasons. Inspect these fields in the original bounded `details`. Preserve whether numbers describe spend, technical conversions, qualified leads or paid orders. An anomaly is a reason to investigate; an observational comparison does not establish causality. The evidence may include a retained marketing matrix; read its manifest and the necessary complete row pages with existing matrix tools, retaining each source's attribution and unknown cells.

Use the backend priority within its actual page, then consider which observation can affect this request: first a blocker of the evidence needed for this decision, then a relevant goal/risk, then a supported opportunity. Follow pages where the relevant signal is outside the preview. Group an ongoing incident and related observations into one useful explanation, but preserve a separate exact response/reference for each observation used. A newer observation does not inherit an earlier conclusion without checking its changed basis. Read earlier Work through `last_response` instead of repeating the same unresolved alert.

Source `pending` (including a goal card `refresh_pending`) means an admitted refresh or calculation has not finished. Read the actual `source_refreshes` owner job locators and their states. Restore the returned owner job locator and perform its supported bounded read; waiting is not failure, an observed zero or unchanged performance. `unavailable` identifies an actual failure, denied source or missing prerequisite. Report its exact limitation when it changes the requested result. A stale or superseded observation can be reviewed as historical/not applicable; it cannot establish current health. For an unfinished assigned analysis save intermediate Work with `keep_pending`; do not acknowledge delivery.

For every material response, explain the actual metric/scope/window and evidence limitation, how it affects the user's present decision, and one useful next check. A `deferred` disposition requires `Work.next_step` or an existing continuation revisit. Keep the three response fields `signal_id`, `disposition` and `reason`; put timing and conditions in the existing next-step/continuation fields. Preserve unrelated active decisions while saving the complete continuation.

The server advances technical source/analytics jobs while the external host is closed. An agent considers the resulting signals on its next real turn or a separately verified host recurrence. New meaningful changes, new blockers and recovery follow the user's notification instruction; unchanged incidents do not justify repeated alerts. No automatic observation supplies new provider, money, publication or messaging authority.
