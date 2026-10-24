# Behavior, rendered pages and form diagnostics

Use for «почему посетители не доходят до заявки?», a JS-only CTA/form, a mobile defect, Webvisor or click/scroll maps. Obtain relevant evidence yourself through available authorized tools and deliver a grounded diagnosis/correction. A copy edit is one possible result; missing native data does not default to a client screenshot or manual report.

| Question | Smallest useful source | What it establishes |
| --- | --- | --- |
| Which cohort deserves attention? | Existing exact [page observations](conversion-workflow.md#connected-r1-ad-match-entry-cohort-change-return) or [Logs](source-metrika-logs.md) | Aggregate visits/events; not the failing element |
| What did visitors do? | Installed connector or authorized provider browser UI exposing the actual recording, map or form report | Behavior within its period/filter/sample; not causal loss |
| Can a failure be reproduced? | Host browser, rendered DOM/screenshot and available read-only runtime/console/network tools | Current interaction in that browser/viewport; not visitor prevalence or CRM delivery |

Native landing capture supplies text/links; native Logs supplies visit/goal aggregates. Neither supplies Webvisor recordings, maps or a field funnel. Do not invent an API, tool or report. A browser observation has its own provenance; it is not an immutable Tactis publication.

Reuse known context, capabilities and applicable instructions. Inspect host capabilities/documentation only for the missing piece. Prefer an existing service connector for a supported read; otherwise use the authorized browser for the exact site/resource. Browser and Tactis source access are distinct. If access is missing, use the normal connection path and ask only for the unresolved step. A public-page reproduction need not wait for analytics access.

Choose the shortest useful inspection. Analytics evidence keeps its actual counter/page, period, filters and sample/availability; inspect only the relevant map or purposeful recordings. One abandonment or a click concentration does not measure total lost leads. Summarize behavior and omit personal visitor/contact data.

On the page, follow the rendered CTA/visitor transition using current visible controls. Inspect the relevant viewport/device when supported; desktop evidence does not prove mobile behavior. For a failure, read the precise DOM/field constraints, visible validation, console error or relevant request/status. Runtime can reveal `patternMismatch`; console/network evidence keeps its observation interval and completeness. Avoid unrelated state/private request bodies. Use ordinary interaction, not internal function calls, disabled validation, DOM mutation or manufactured analytics events.

Proceed with ordinary inspection and reversible interaction within the request. Use synthetic values in an appropriate test context; creating a real lead/order or another external record requires the corresponding authorization, including autosave before submit. Synthetic success, HTTP success, a provider event and a retained CRM inquiry prove different stages.

Return the obstacle, exact transition/location, evidence and first practical correction with its acceptance check. Keep URL/time, relevant browser/viewport and analytics period/sample. Separate reproduction, visitor observation, plausible mechanism and measured impact. No obligatory questionnaire, checklist, Work or report is needed; existing save rules apply only when persistence is relevant. If direct sources fail, name the actual limitation, continue the independently useful result and request only the unresolved fact/access action. Client fragments are an attributed fallback.

**Synthetic example:** a JS form suggests `+7 (999) 111-22-33`, but its field has `pattern="[0-9]{10}"`. The shown format produces native validation and `patternMismatch=true`; ten digits reach local success. Align phone normalization/validation with the displayed format and retain invalid-input feedback. Recheck both inputs. This proves a reproduced format conflict, not visitor losses or production delivery.
