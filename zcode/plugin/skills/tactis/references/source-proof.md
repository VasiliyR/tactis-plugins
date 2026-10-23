# Exact proof, source identity and pinned bundles

Use only for the missing historical/source proof or independent pinned reads. Ordinary metrics use [retained statistics](source-history.md).

## Addressed proof and historical readers

Use a known exact locator directly; discovery and proof reading answer different questions. These readers do not grant action permission or repair an unavailable source.

| Needed value / question | Reader and locator source | Retain / boundary |
| --- | --- | --- |
| Does this saved scope still belong to this account/selected objects? | `get_native_scope(project_id, proof_id)`; proof_id from actual `prepare_native_scope` or the saved Plan analysis_basis | Mode, request, source/root fingerprints and exact selected ancestry. A read-only membership proof is not current write authority, object version or user choice. |
| Exact analysis evidence for this campaign | `get_analysis_campaign_reference(project_id, publication_id, campaign_native_id)`; Analysis ID from saved Work/analysis manifest and campaign from its catalog | Publication fingerprint, evidence_refs, goal identity, comparison scope and inventory linkage. A Daygrain ID is not an Analysis ID. |
| Exact dossier subject/evidence for a hypothesis | `get_dossier_campaign_reference(project_id, publication_id, campaign_native_id, evidence_refs=...)`; refs from already read dossier/family rows | Dossier/publication/input fingerprints, original analysis, family coverage and selected goal. Omit unused refs or request only actual available refs; a candidate ID does not become an observation. |
| Historical configuration identity or exact source details | `get_configuration_manifest(project_id, publication_id)` using the saved **Configuration** ID | Frozen source/inventory/family identity, captured_at and original evidence. Current configuration is only discovery, never a replacement for saved history. |
| Historical statistics, binding or coverage explanation | `get_daygrain_manifest(project_id, publication_id)` using the saved **Daygrain** ID; include bounded coverage only when needed | Original through/state/source/window and partial limits. Historical manifest reading does not refresh old facts or establish a current analysis basis. |

`get_current_configuration` now returns a compact current locator by default. Pin its ID and read the immutable manifest only when exact source/binding/fingerprint details are needed. `compact=false` explicitly restores the full current manifest projection; it does not make that latest projection the historical one. Brief publication summaries can supply ready/current locators and captured_at/through/state; they are readiness hints, not proof of complete metrics or business meaning. Current Daygrain and Configuration always retain their separate typed domains.

Saved historical readers are subject to present authorized read rights and owner checks. A current-head prerequisite for a **new action** can reject an old basis; do not silently switch the evidence to latest to make it pass. Preserve the historical conclusion and resolve only the new action's actual prerequisite.

## Bundle pinned reads

Use `read_evidence_bundle(project_id, items)` for a few already known independent pinned reads: `get_analysis_manifest`, `get_analysis_campaign_reference`, `get_dossier_manifest`, `get_campaign_dossier`, `get_daygrain_manifest`, `get_daygrain_values`, `get_landing_manifest`, `get_landing_page`. Nested items use bare tool names and their actual arguments; dossier family pages pass `family` with `limit`/`offset`, while omitted family reads needed campaign metadata; landing uses `artifact_id`. A known family needs no preceding metadata read. Dependent discovery cannot be combined before its IDs are known. Configuration/catalog/metrics/Work/operations/CRM/Lifecycle are outside this whitelist. The bundle validates all inputs before IO, deduplicates identical reads and runs at most three concurrently under one deadline. Keep pages small; preserve successful siblings when an item is unavailable/deadline/oversize, and drill down only into that exact item. Its bounded response does not turn partial coverage into complete coverage. Per-item success preserves its original coverage/nulls, not complete source coverage.
