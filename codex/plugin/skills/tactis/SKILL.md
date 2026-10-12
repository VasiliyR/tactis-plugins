---
name: tactis
description: >-
  Начни или продолжи работу по клиенту в Tactis: восстанови контекст, выбери приоритет среди задач маркетинга, подготовь программу роста или согласуй работу по нескольким проектам. Используй для «с чего начать», «продолжи работу по клиенту» и смешанных задач; для конкретного результата выбери профильный навык Tactis.
metadata:
  version: tactis-method-0.4
---

# Tactis — работа по клиенту и выбор следующего шага

For real files, sharing, imports/planning, CRM, finite monitoring, audiences and feed/Webmaster work, read [the ten platform scenarios](references/platform-workflow.md) when entering that task. Reuse exact saved versions and current permissions.

Present ordinary analysis in chat. For advertising charts, comparisons and analytical tables, use [Tactis visual analysis](../tactis-visual-analysis/SKILL.md). Create separate reports or exports only when the user requests them; recording Work and evidence does not require generating a document.

Use the user's selected project and current server capabilities. The user's request takes precedence over methodological preferences. Server permissions, source versions and provider constraints still govern execution.

Tactis connects the external agent's marketing work to authorized client data, supported actions and durable memory. Before first using connected client context in a chat, read [platform and client entry](references/session-entry.md): Tactis tool discovery and compatibility → authorized project/account → confirmed context and relevant saved Work. Reuse that context across products and the visual skill; read it again only when scope or a relevant dependency changes.

Use a short route when it answers the question. Open the matching product procedure when entering its substantive work, and its supporting references only for that stage. A product name does not establish a source, tool, permission or completed external action. Query actual capabilities and operation schemas before constructing a change payload. Give the useful supported part when a prerequisite is missing, preserving the exact material and next step.

| Client-wide request | Short route |
| --- | --- |
| New client / «С чего начать?» | [Onboarding](references/onboarding.md): recover existing choices and sources, deliver and save the first useful result. A new client does not require a full audit. |
| Several clients / positioning or offer | [Portfolio and offer](references/portfolio-offer.md): authorized per-client scopes or a grounded offer hypothesis and first material; no invented aggregate reader or market claim. |
| Continue saved work | Read the relevant full head and exact material through [durable continuation](references/durable-continuation.md). Known Work uses `get_work_session(project_id, work_session_id)`; older material is discovered through `get_work_session(project_id, collection="work_sessions", ...)`. |
| Choose a marketing priority or growth programme across tasks | [Growth](references/growth-workflow.md): select the supported constraint, a feasible programme and first material; enter the relevant subject procedure only for that stage. |
| Files, galleries, cross-channel imports/media plans, CRM/offline, finite monitoring, audiences or feeds/Webmaster | [Ten platform scenarios](references/platform-workflow.md): actual tools, exact versions, secure setup and effect boundaries. |
| Return regularly to agreed work | [Automation](references/automation-workflow.md): retain the instruction and useful due result; actual scheduling depends on the host. An unverified schedule is not an active recurring assignment. |

For a focused request, use the matching entry below directly. Each entry shares the same client context, tools and memory; switching does not require another onboarding, a separate agent or loading every skill. Preserve the user's explicit task and existing applicable choices. In mixed work, read the specialist only when its substantive result is needed.

| Requested result | Focused skill |
| --- | --- |
| Create or launch a supported campaign from an offer | [Campaign launch](../tactis-campaign-launch/SKILL.md) |
| Audit existing advertising, explain rising CPA or choose an optimization | [Ads audit](../tactis-ads-audit/SKILL.md) |
| Analyze metrics, select a meaningful goal or check conversion measurement | [Measurement analysis](../tactis-measurement-analysis/SKILL.md) |
| Review one landing page and prepare a useful conversion edit | [Landing review](../tactis-landing-review/SKILL.md) |
| Prepare advertising copy and exact grounded variants | [Ad copy](../tactis-ad-copy/SKILL.md) |
| Create a requested separate client report | [Client report](../tactis-client-report/SKILL.md) |
| Show analytical charts or tables | [Visual analysis](../tactis-visual-analysis/SKILL.md) |

For several already known, independent, small pinned references, `read_evidence_bundle` can combine the eight supported analysis/dossier/Daygrain/landing readers. It does not accept configuration, metrics, Work, operations, CRM or Lifecycle readers; see [foundation reads](references/foundation-reads.md). A successful bundle does not make partial source data complete.

| User goal and connected work | Product procedure |
| --- | --- |
| Diagnose advertising → choose an improvement or prepare SEARCH → apply an exact supported plan → review the result | [Tactis Ads](references/ads-workflow.md) |
| Control meaningful changes or produce weekly material → revisit a saved decision → change or stop the instruction | [Tactis Automation](references/automation-workflow.md) |
| Understand audience conditions and exclusions → choose for an offer → prepare the handoff → revisit comparable observations | [Tactis Audience](references/audience-workflow.md) |
| Brief and concepts → complete text package → exact chosen version → application or feedback | [Tactis Creative](references/creative-workflow.md) |
| Create a requested client report from saved evidence and Work → read its private artifact and limitations | [Tactis Reports](references/mvp-workflow.md), “Frozen measurements and private reports” |
| Compare economics → set a paid-sale cost limit or constrained budget proposal → revisit payments, refunds and costs | [Tactis Profit](references/profit-workflow.md) |
| Choose a hypothesis and design → save the material and original criterion → read actual application/measurement → decide and reuse | [Tactis Experiments](references/experiments-workflow.md) |
| Match the offer and page → inspect entry observations → prepare an exact page edit → verify the public version and comparable observations | [Tactis Conversion](references/conversion-workflow.md) |
| Prioritize pages and demand → brief and first material → editorial/public review → search observations and next work | [Tactis SEO](references/seo-workflow.md) |
| Inquiry quality and processing → a useful assignment → actual execution evidence → paid outcomes and next check | [Tactis Sales](references/sales-workflow.md) |
| Next purchase or winback → group rule and contact materials → eligibility/application evidence → matched repeat payments and next decision | [Tactis Lifecycle](references/lifecycle-workflow.md) |
| Choose a growth constraint → a feasible programme and first material → subject work and progress → revise priorities/resources | [Tactis Growth](references/growth-workflow.md) |

For connected advertising facts, use [foundation reads](references/foundation-reads.md) with the coverage needed by the decision. An absent brief does not block a supported traffic/spend assessment. For exact Ads preparation/execution use [current actions](references/current-actions.md); for deeper site, goal, query, negative or campaign reasoning use [profiled reasoning](references/profiled-reasoning.md). The matching [MVP workflow](references/mvp-workflow.md) section supplies common intake, CRM, measurement or report mechanics when needed. Native IDs stay exact decimal strings throughout nested MCP payloads and JavaScript. Historical artifacts retain their original method version and provenance.

## Continue across products in the same chat

Use a transition when it advances the user's task. Begin with its relevant stage and read the next product's procedure only when reaching it. The same external agent performs the work; there is no separate agent call or requirement to visit every product. The linked procedures contain the concrete handoff and missing-data branches.

| Scenario | Route and decision |
| --- | --- |
| **X1: advertise an offer for the right audience** | [Audience](references/audience-workflow.md) → [Creative](references/creative-workflow.md) → [Ads](references/ads-workflow.md) → [Experiments](references/experiments-workflow.md). Carry the selected condition, offer and exact text. Prepared audience work does not mean attach/suspend was performed. |
| **X2: improve expensive advertising** | [Ads](references/ads-workflow.md) → [Conversion](references/conversion-workflow.md) or [Sales](references/sales-workflow.md) according to the supported question → relevant [Creative](references/creative-workflow.md), [Profit](references/profit-workflow.md) or [Experiments](references/experiments-workflow.md) work. Choose the evidenced loss or unknown; high event CPA alone does not prove poor sales or a broken page. |
| **X3: grow repeat sales with viable economics** | [Sales](references/sales-workflow.md) → [Lifecycle](references/lifecycle-workflow.md) → relevant [Creative](references/creative-workflow.md) and [Profit](references/profit-workflow.md) work. Use matched paid purchases and the actual selected group/application evidence; CRM totals cannot recover repeat buyers. |
| **X4: attract demand through a service page** | [SEO](references/seo-workflow.md) → relevant [Conversion](references/conversion-workflow.md) and [Creative](references/creative-workflow.md) work → SEO observations, or [Reports](references/mvp-workflow.md) if requested. Preserve the selected page/brief; all-entry observations do not become organic and publication does not prove indexing. |
| **X5: carry a growth programme through to decisions** | [Growth](references/growth-workflow.md) → the chosen subject product → relevant [Experiments](references/experiments-workflow.md) or [Automation](references/automation-workflow.md) follow-up → Growth, or [Reports](references/mvp-workflow.md) if requested. Start the feasible work now; an unverified host schedule is not an active recurring assignment. |

At a transition, carry exact project/account, source and Work locators, the complete chosen text/rule, existing user choice, actual state, limits and next check. Read the saved material instead of regenerating it. Local material labels are not typed publications. Preserve unrelated active work.

Use [the shared action/persistence contract](references/invariants.md) at a change, save, recovery or return: **freeze → applicable choice → execute → readback**, exact command/digest recovery, unknown versus zero, scope/units/VAT/timezone/attribution, continuation CAS and `keep_pending`. Automatically save substantive Work and full continuation; routine successful persistence stays silent. An explicit business fact/correction is the applicable choice for those exact context values. Inferred assumptions remain uncertain. Read the current business generation before writes and use explicit replacement only for a different business. A recommendation or host permission never supplies the person's advertising/money/access choice. Reuse an already applicable exact choice.

For a prospective controlled comparison, go directly to [the assisted recipe](references/assisted-experiment.md); real external allocation and attestations remain distinct from provider verification. For an existing due task's host-bound claim/result/ack, use [proactive delivery](references/proactive-delivery.md); it does not create scheduling or a hidden model. [Three synthetic traces](references/workflow-traces.md) illustrate diagnosis, exact-change recovery and weekly return; they are instructional examples, not executed proof.

Another host authenticates separately and reads the same exact server artifacts. Keep useful project/Work/Plan/Application/report locators in the handoff; copied credentials and chat history do not grant continuity or authority.
