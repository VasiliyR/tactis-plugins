# Work save validation and recovery

Read this only for a rejected save, conflict, unknown response, capacity problem or an exact large-Work read. Ordinary successful saving ends at its committed receipt.

## Fit a rejected or oversized command

Use the actual `record_work_session` input schema already supplied by the host; fetch one exact `get_tool_contract` only when a needed constraint is absent or conflicts. `summary` is the concise result, not the full report, JSON payload or repeated evidence inventory. Aim for at most 1500 Unicode characters, within the actual schema maximum (currently 4000). Count the final text before the call and check the complete command's required fields, per-field lengths and item limits against that schema.

Keep exact evidence in `foundation_refs`/`platform_refs`, caveats in `limitations`, and the next check in `next_step`, within their own schema limits. Preserve a complete chosen material in its supported body or an exact-readable saved material and retain its reference. Do not drop references, uncertainty or the decision criterion to shorten the summary. Remove duplicated prose and rewrite semantically; do not slice an overlong string or use memory, profile or continuation fields merely as overflow storage.

If the command does not fit, revise it before sending. An input-schema rejection before admission has not saved the result; correct the rejected arguments within the same task and current authority. An uncertain transport outcome instead follows the exact original key/payload recovery procedure below. Field checks do not replace current-reference, rights or continuation checks at admission.

For `continuation_delta_invalid`, compare the rejected command with the current compact form: `continuation.mode="delta"`, full typed roots in the top-level reference arrays and exact reference keys inside entries. Keep expected head, revisions and unrelated carried entries intact. Removing continuation may save a standalone Work, but does not update the head; retain that saved Work and finish or report the pending head update without claiming the result was lost.


On a head/context/generation conflict, read the current state, reconcile meaning and submit a new command on that base. When revising a carried entry on the new base, `supersedes` uses the current head Work ID and that entry's current ID/revision; `carried_from` is provenance, not the replacement base. On an unknown transport outcome, replay the same original key/payload before any new identity. Replays cannot rewind a later head. If saving failed or remains unresolved, explain it; routine successful saving stays silent.

Historical snapshot and separate `continuation_delta` payloads can remain in retained client commands and exact retries; preserve those original bytes for recovery. They are not the shape for a new native call. New calls use compact `continuation` from the current schema; older-server recovery belongs in [compatibility recovery](plugin-updates.md). [The snapshot example](continuation-example.json) and [Work example](automatic-memory-example.json) are synthetic schema examples; use the current callable shape and real client references, never their invented evidence.


## Bounded native Work recovery

An exact large Work can return `workspace.work.wire-chunk.1`. Keep the fragments already received when entering this recovery; follow the returned `next.tool` and exact `next.arguments` until `complete=true` and `next=null`. Concatenate raw fragments in `body_offset` order, verify `wire_sha256`, then parse. Offsets count Unicode characters; the wire hash and original saved digest have distinct roles. A summary or truncated page does not replace the original requested material. Do this when reading that material, not to revalidate every successful save.

For a provider effect use [execution recovery](current-actions.md#recover-a-lost-execution-response). A quota due time means waiting for the same job, never reconnecting or resending a write to bypass it.

## Snapshot capacity

The complete snapshot must fit 40 entries and 32768 canonical UTF-8 bytes after reference expansion. Delta carries unchanged entries server-side. If final capacity rejects a save, first remove duplicated prose from your new or revised entries while preserving their meaning, uncertainty and next step; reuse exact references to results already saved. Do not copy the full report into continuation or create a new file merely to fit this limit. Preserve other active entries. If this still cannot fit, inspect the relevant head and archive only genuinely resolved entries with exact predecessors and reasons. A useful standalone Work can preserve the result without advancing the head; state that pending head update explicitly. Do not silently drop active decisions or reread unrelated source evidence.
