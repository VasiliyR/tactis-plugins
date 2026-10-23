# Host rendering and evidence portability

Discover the current host's available presentation tools. This skill supplies advertising interpretation and chart selection; it does not install a rendering engine or require a proprietary visual tool. Codex, ZCode and Claude Code builds include this skill; previously installed copies require their own update.

| Available surface | Delivery |
| --- | --- |
| Native interactive inline visual | Use the host's documented chart/visualization capability and its output contract. Keep filtering and hovering local; no advertising writes from controls |
| Inline images with local execution | Use an available plotting library to render and inspect a chart, then embed it by the host's supported mechanism. A local render asset is not a separate client report |
| Markdown only | Use a readable table, concise comparison or simple labeled bars. Explain unavailable interactivity without blocking the analysis |
| Explicit document/export request | Use the supported report/export tools for their actual schemas and formats. Do not imply the fixed backend HTML/PDF renderer accepts arbitrary layouts or interactive charts |

When a host supplies a visualize skill, use its actual instructions for inline rendering rather than assuming its paths, APIs or directives work elsewhere. Never require the user to install a second skill manually if the Tactis plugin already supplies this methodology. A package build does not establish installed-host rendering acceptance.

If a renderer is unavailable or denied, use the supported table or labeled-bar fallback in that answer. Reuse that delivered visual on a short continuation; do not retry the same blocked renderer or promise an image unless a changed capability is established. Say a chart or image was shown only when the actual visible output exists; a sentence describing an absent chart is not a visual.

## Presentation checks

- Label axes, metrics, units, period and event meaning. Use direct labels or a stable legend; never use color as the sole carrier of meaning.
- Keep bar baselines at zero. A restricted line/scatter axis can be useful when its scale is explicit. Match scales across panels intended for comparison.
- Make missing values visually distinct, with no continuous measured line through missing periods. Keep scenario/forecast styling distinct from observations.
- Keep the main conclusion and essential numbers available without hover. Support readable labels and keyboard/touch interactions where the host permits them; use a table alternative if needed.
- Inspect the rendered result at normal and narrow widths. Check clipped labels, overlapping marks, legend behavior and the primary interaction. A successful library import alone is not a rendering check.
- Tooltips and filters must use the same frozen dataset as visible marks. Filtering cannot silently change period, attribution, denominators or the user's selected account.
- Do not send client data to an external chart service or embed secret-bearing links. Use the selected host's authorized data/rendering boundary and minimal relevant data.

## Portable analytical context

Retain the existing owner references behind a chart, its filters, aggregation and units with the work context when relevant. These are not a new backend DTO: use the actual Work/evidence schemas, not an invented payload. Another host can reconstruct the meaning from the references even if it uses a different renderer. Never claim that a visual's local state is durable Work or authorization.

A visual drill-down may ask the agent to inspect a selected segment. Before a proposed ad change, the agent shows its exact scope and effect, asks for the user's choice in chat and waits. Ordinary server write guards and provider readback still apply. A chart selection alone is not that choice.
