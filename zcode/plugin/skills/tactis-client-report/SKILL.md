---
name: tactis-client-report
description: >-
  Подготовь клиентский отчёт Tactis, опубликуй готовую HTML-версию по ссылке или отзови публикацию. Используй для запросов «сделай отчёт клиенту», «подготовь PDF», «дай ссылку на отчёт» и «закрой доступ к ссылке». Короткий обзор остаётся в чате.
metadata:
  version: tactis-client-report-0.1
---

# Tactis — отчёт для решения клиента

Produce the requested client deliverable from actual saved evidence and Work. Use the shared [session entry](../tactis/references/session-entry.md) once for connected scope, then reuse the selected project/account and known recipient, period and purpose. Follow [shared invariants](../tactis/references/invariants.md) for access, source integrity and saving. An ordinary status question does not require generating a document.

## Shape the report around the decision

Start from what the client needs to decide: continue, correct a problem, approve a next step or review a completed change. Reuse the relevant exact `get_work_session` and its evidence references. Select `overview`, `audit`, `launch` or `experiment` from the requested subject; do not run a new full audit merely to format an existing result.

Read [the decision-report method](../tactis/references/marketing-review.md#report-for-a-decision) for the recipient-facing narrative. Give the known result and comparison, interpretation with alternatives, material uncertainty, proposed next action and its check. Distinguish what was prepared, what actually applied and what has been observed. Keep period, event meaning, attribution, currency/VAT, coverage and maturity beside the relevant numbers. Use supplied branding without inventing the agency, recipient or business claims.

Use exact owner-backed Analysis numbers rather than recomputing or improving a report snapshot. Do not merge technical events with qualified leads or paid sales, extrapolate incomplete coverage, or describe a before/after observation as proved causal uplift. Include the limitation where it affects the decision, not only in a final footnote.

## Create the requested document

Read [private report mechanics](../tactis/references/mvp-workflow.md#frozen-measurements-and-private-reports) when generating HTML/PDF. The current `create_analysis_report` path uses exact `work_session_id`, `analysis_publication_id`, supported mode, bounded narrative and branding. Its renderer owns the fixed HTML/PDF presentation; author prose, not arbitrary HTML/JS or replacement numeric fields.

| Mode | Necessary retained subject |
| --- | --- |
| Overview or audit | Saved Work with its compatible exact Analysis basis |
| Launch | The exact Application plus compatible Analysis/Work; include its measurement when a numerical intent exists. A technical PAUSED draft or pending observation keeps that state |
| Experiment | Exact Application, retained native outcome, measurement and corresponding Analysis cited in Work; an elapsed date alone does not establish a mature covered outcome |

Save and read back the substantive Work before creating its document, using [durable continuation](../tactis/references/durable-continuation.md). Reuse a matching existing report when the request concerns that version. Otherwise call the actual available creation tool and read `get_client_report` for its resulting metadata and authenticated HTML/PDF links. A creation request or lost response is not proof of a completed file.

## Publish or revoke a saved HTML version

An explicit request to publish authorizes the requested link, not message delivery or a public replacement of the source document. Read [publication mechanics](../tactis/references/mvp-workflow.md#publish-a-saved-html-report) and inspect the actual tools. Use the exact existing `report_id` from `get_client_report`; this path cannot upload an arbitrary HTML page, expose PDF, render live numbers or accept comments.

Reuse the user's selected access policy: `fixed_10_days` expires at the returned timestamp, while `while_subscription_active` follows the organization's current subscription and can become inactive. If the intended duration is unclear and changes the requested result, resolve that choice before publication. Use an optional short `title` from the actual report/request, without inventing dates; it names the link and does not rewrite HTML. Keep one `command_key` for the exact `project_id`, `report_id`, policy and title. Call `publish_client_report`, then `get_report_publication(project_id, publication_id)` to verify its actual version, status, `public_url`, policy and `expires_at`. Return the real link and its access condition; only an `active` readback establishes availability. A lost response is recovered with the same command key/payload, never a fresh publication.

For an existing link, use `list_report_publications(project_id, limit, offset)` only when its exact locator is unknown; honor `next_offset`, then read the chosen publication. On an explicit revoke request, call `revoke_report_publication` for that exact locator and read back `status=revoked`. Revoking the link preserves the report and its private artifacts; do not republish it automatically. Read/replay/revoke remain subject to current authority when the subscription expires; a new publication requires active access. Preserve exact report/publication locators and the selected policy in substantive Work when saving is permitted.

## Missing data and delivery

If a saved report basis is missing, read or prepare only the evidence needed for this subject and period through [foundation reads](../tactis/references/foundation-reads.md). Partial Analysis can support a report with its explicit known part and limitations; missing access or a required experiment outcome cannot be hidden by narrative. Deliver the useful supported review and name the exact remaining prerequisite when a document cannot be created.

A CRM-only or portfolio summary without the required supported Analysis is a chat deliverable, not a fabricated report. User-supplied numbers can support an attributed provisional review; they are not Tactis owner publications. For an ordinary overview, use [visual analysis](../tactis-visual-analysis/SKILL.md) in chat when a chart/table helps.

Return the requested private artifact or verified public link with its actual version, covered period, concise result and applicable access condition. Document creation and link publication do not send the report to the client. Use only delivery mechanisms actually present in the current catalog and separately authorized by the user's request. Preserve the report locator and next check in saved Work so a new chat can retrieve the same version.
