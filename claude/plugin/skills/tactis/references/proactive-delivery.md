# Finish a due task under the existing delivery policy

Use when an external host turn is already running and a due Tactis task has an enabled policy bound to that host. A policy does not create a native host recurrence or start a hidden model. [Automation](automation-workflow.md) owns the user's recurring instruction; this recipe owns only claim/result/ack for an existing task.

| Step | Exact tool / values | Meaning and next step |
| --- | --- | --- |
| Policy | `get_proactive_delivery_policy(project_id)` | Read policy, polling_status and host limitations. Ready polling is not an active scheduler. Disabled/unavailable/mismatched authority requires its authorized human settings path, not a policy/grant change by the agent. |
| Claim | `claim_proactive_delivery(project_id)` | `claimed` returns actual delivery_id, private lease_token, claim_until, expiry and task; `quiet_hours`/`empty` returns no task. Do not fabricate a lease or execute old expired work. |
| Inspect/recover | `get_proactive_delivery(project_id, delivery_id)` | Actual claim/delivery status and Work locator. The reader deliberately omits the lease token. A lost claim response cannot be reconstructed from a guessed token; keep claim/result unconfirmed and use the real lease/recovery state. |
| Perform and save | Matching task recipe → `record_work_session` → exact `get_work_session` | Complete the task's requested result with its exact task_id and `task_resolution="complete"`; save the useful compact result and evidence, then verify it. |
| Acknowledge | `ack_proactive_delivery(project_id, delivery_id, lease_token, work_session_id)` | Use the **same returned current lease** and actual task-linked saved Work ID; then read `get_proactive_delivery` again. `delivered` is agent acknowledgement, not evidence the person read a notification. |

Private lease tokens are temporary operational values: preserve them only where required to complete this run; never include them in user materials, Work, reports or public traces. Ack does not use a guessed run ID or native schedule ID. Task, delivery, Work and schedule locators have different domains.

Read the exact assigned task and restore its relevant Work before collecting data. Stay within its actual scope and rights. A source job still pending or a mature window still future can produce useful intermediate Work, but does not satisfy a task that asked for its completed result. With the exposed current contract, retain `task_id` and `task_resolution="keep_pending"`; do **not** ack completion. If the installed schema lacks keep_pending, save ordinary Work without task_id and retain the still-open locator. This follows the [shared task gates](invariants.md).

Do not ack until durable task result and exact readback exist. A rejected save is unsaved; an ambiguous one needs same-command recovery before another save. A stale lease (`delivery_claim_stale`) requires reading delivery/current task state; do not reuse an expired token, create another task or save a duplicate merely to obtain an ack. A lost ack response can be resolved by exact delivery read; an identical valid ack is idempotent. A delivered record must link the intended task Work, not an unrelated note.

Notify only according to the already chosen host instruction: a new meaningful change/blocker/recovery for exception control, or the requested weekly material at its cadence. Written “quiet” text does not prove host notification suppression. When the host is closed, tasks persist and technical workers may advance sources, but interpretation waits for the next actual model turn. Another authenticated host can read Work; its identity does not inherit the original policy lease or schedule.
