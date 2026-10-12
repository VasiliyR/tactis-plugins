---
name: tactis
description: >-
  Разбери результат рекламы в Tactis, выбери следующий шаг, подготовь точные тексты или поддержанное изменение и продолжи сохранённую работу по клиенту. Используй для вопросов «почему вырос CPA», «что улучшить первым», «подготовь поисковую рекламу», «сделай недельный обзор», проверки измерения и связанных задач маркетолога. Подключённые источники и реальные права определяют доступный результат; графики и аналитические таблицы ведёт tactis-visual-analysis.
metadata:
  version: tactis-method-0.4
---

# Tactis — продукты для маркетинговой работы

Present ordinary analysis in chat. For advertising charts, comparisons and analytical tables, use [Tactis visual analysis](../tactis-visual-analysis/SKILL.md). Create separate reports or exports only when the user requests them; recording Work and evidence does not require generating a document.

Use the user's selected project and current server capabilities. The user's request takes precedence over methodological preferences. Server permissions, source versions and provider constraints still govern execution.

Tactis connects the external agent's marketing work to authorized client data, supported actions and durable memory. Before first using connected client context in a chat, read [platform and client entry](references/session-entry.md): Tactis tool discovery and compatibility → authorized project/account → confirmed context and relevant saved Work. Reuse that context across products and the visual skill; read it again only when scope or a relevant dependency changes.

Use a short route when it answers the question. Open the matching product procedure when entering its substantive work, and its supporting references only for that stage. A product name does not establish a source, tool, permission or completed external action. Query actual capabilities and operation schemas before constructing a change payload. Give the useful supported part when a prerequisite is missing, preserving the exact material and next step.

| Ordinary request | Short route |
| --- | --- |
| New client / «С чего начать?» / are these events meaningful? | [Onboarding and measurement check](references/onboarding.md): recover existing choices, check the actual source/event/coverage, deliver and save the first useful result. |
| «Почему вырос CPA», impressions disappeared, irrelevant SEARCH queries or NETWORK placements | [Ten symptom routes](references/optimization-recipes.md): select the relevant evidence and supported next result; a symptom does not authorize an automatic write. |
| Prepare or launch SEARCH from an offer | [Campaign launch](references/campaign-launch.md): complete material → permitted PAUSED graph/readback → separate moderation and finite launch choices → actual observation. |
| Audit / daily, weekly or monthly review / report for a decision | [Marketing review](references/marketing-review.md): addressed checklist, one cadence, recipient's decision and exact saved material; a separate report only when requested. |
| Several clients / positioning or offer | [Portfolio and offer](references/portfolio-offer.md): authorized per-client scopes or a grounded offer hypothesis and first material; no invented aggregate reader or market claim. |
| Advertising got worse: what should we check and do first? / «Результат рекламы ухудшился» | Follow [performance diagnosis](references/performance-diagnosis.md): compare covered windows, identify the main known loss, inspect the relevant evidence, and save up to three priorities with one useful next step. |
| How is advertising doing? | In the resolved project/account, read exact-window metrics with `project_id` and the **Daygrain** `publication_id` through [foundation reads](references/foundation-reads.md). Metrics include campaign names; configuration status/settings require their own relevant readers. Inspect coverage and only the receipts needed by the question. |
| Continue saved work | Read the relevant full head and exact material through [durable continuation](references/durable-continuation.md). Known Work uses `get_work_session(project_id, work_session_id)`; older material is discovered through `get_work_session(project_id, collection="work_sessions", ...)`. |
| Prepare useful material | Read the selected Work and exact retained landing spans, then author the requested text or recommendation. Enter [Creative](references/creative-workflow.md) or the relevant product procedure for a full package. Read action capabilities and current before-state when preparing a provider change; a text request does not imply a full audit, capture, execution or separate report. |

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
