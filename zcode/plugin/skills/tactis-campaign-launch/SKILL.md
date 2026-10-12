---
name: tactis-campaign-launch
description: >-
  Подготовь и создай рекламную кампанию Директа из предложения или сайта в Tactis. Используй для запросов «создай поисковую рекламу», «подготовь кампанию в РСЯ», «отправь на модерацию» и «запусти эту кампанию». Доведи работу до запрошенного этапа: готовый материал, структура PAUSED, модерация или отдельный запуск показов.
metadata:
  version: tactis-method-0.4
---

# Tactis — создание и запуск кампаний

For real files, sharing, imports/planning, CRM, finite monitoring, audiences and feed/Webmaster work, read [the ten platform scenarios](../tactis/references/platform-workflow.md) when entering that task. Reuse exact saved versions and current permissions.

Deliver the requested campaign stage, starting from the client's offer or existing saved draft. Reuse the shared [session entry](../tactis/references/session-entry.md) for the authorized project/account, confirmed context and relevant Work. A client already resolved in this chat does not need another brief. Follow [shared invariants](../tactis/references/invariants.md) for rights, exact choices, command identity and readback.

## Build the useful campaign material

Recover the selected offer, landing URL, geography and any chosen copy. Read the relevant retained landing spans, or acquire the one needed document through `prepare_landing_document` → `get_landing_job` → `get_landing_manifest` → `get_landing_page`. Pending acquisition is not page evidence. Attribute website claims; do not turn them into confirmed prices, guarantees or business goals.

Group the actual offer by search intent or the supported NETWORK structure. Prepare complete keywords/negatives where applicable, exact titles/text, destination and selected settings. Explain why the groups and messages fit this offer; preserve already chosen Creative material. Use the operation-specific `get_operations_catalog(..., operation="create_campaign", include_schema=true)` to fit the actual provider shape, rather than writing an unsupported ideal campaign.

Give the complete first material in chat even when creation is blocked. Missing measured demand does not prevent grounded copy: distinguish authored intent from measured frequency. Resolve provider geography through the catalog's region directory when preparing a real plan; an unknown region is not nationwide targeting.

## Advance the selected stage

Read [campaign preparation and launch](../tactis/references/campaign-launch.md) when constructing or continuing a provider plan. It owns geography receipts, landing proof, the Creator money policy and measurement prerequisites. Use [current action mechanics](../tactis/references/current-actions.md) for exact scope, versions, proposal and recovery; load only the relevant section.

| Requested result | Work to complete | Proof to return |
| --- | --- | --- |
| Create a campaign | Actual creator-account scope and current basis → complete supported graph → exact saved Plan and applicable user choice → execute | New IDs and per-object Application readback showing PAUSED creation; queued/partial/unknown keeps its actual state |
| Moderate a created campaign | Read the created objects and current moderation capability → separate exact plan/choice → execute and inspect readiness | Submitted moderation versus actually accepted moderation, with the saved result |
| Start paid delivery | Current created scope, accepted moderation, exact counter/goal, compatible measurement basis and finite money policy → separate launch plan/choice → execute | Application/serving readback and the frozen observation condition |

Current native creation supports SEARCH/NETWORK in the declared UNIFIED_CAMPAIGN/RESPONSIVE_AD shape. Read readiness for this graph; do not infer support for every ad format or strategy. Even PAUSED native creation requires the finite money policy returned by the catalog. Creation or moderation authorization does not authorize spending; a new spending period has its own plan and choice. Retained plans and applicable authorization are reused without repeating completed work.

## Finish or preserve the exact blocker

If the offer, source, geography, money policy, rights or provider shape is missing, deliver the useful supported draft and name the one condition needed for the requested next stage. Ask only for a business choice the saved context cannot resolve. Do not replace a missing goal or numerical launch target with zero, invent an executable Plan, or widen permissions.

Return the actual stage, complete selected material and real Plan/Application IDs when present. After launch, use `get_native_measurement` and the actual retained `get_native_outcome` to distinguish pending maturity, observed results and interpretation; a PAUSED graph does not prove serving or sales.

Save exact material, references, status and one next step using [durable continuation](../tactis/references/durable-continuation.md), then read back the saved Work. On return resume those same objects, not a second campaign. A lost execution response uses the saved identity's read/replay recovery before another effectful request.
