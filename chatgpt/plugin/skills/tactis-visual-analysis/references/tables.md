# Analytical tables in chat

Use ordinary chat tables when they are readable. For many columns, split by question or expose a bounded interactive view if supported. Do not silently truncate the inspected population. Keep numerical units in headings and material limitations close to the affected values.

| Table | Useful columns | Domain requirements |
| --- | --- | --- |
| Diagnosis | Segment; spend; exact event count; qualified leads; cost per qualified lead; limitation | CRM absence is unknown, not zero; retain volume and maturity |
| Period comparison | Metric; previous; current; absolute change; relative change | Matching scope/windows; percentage points for rate differences; relative change from zero undefined |
| Multidimensional pivot | Campaign; device; region; spend; events; compatible ratio | Do not add overlapping audience segments; show coverage and totals |
| Search semantics | Query; matched keyword; intent hypothesis; spend; outcomes; suggested handling | Intent is external interpretation. Brand/informational/low-volume demand is not automatically waste |
| Negative conflicts | Exact negative phrase/operators; potentially blocked useful intent; evidence; proposed action | Complete stated set, exact before/remove/add scope; unresolved rows not implicitly safe |
| Creative/landing | Ad claim; landing evidence; supported offer; observed metric; proposed variant | No fabricated benefits, prices or causal winners from unequal exposure |
| Decisions | Observation; hypothesis; alternatives; proposed action; possible harm; next check | Explicit distinction between fact, inference and proposed change |
| Change preview | Exact object; before; after; evidence; operation state | Show the proposed change for an explicit chat choice; dispatch and provider effect remain separate |
| Experiments | Hypothesis; allocation; primary metric; sample/exposure; estimate/interval; guardrails; status | No winner without supported design and sufficient evidence |
| Data quality | Source; period; freshness; coverage; missingness; linkage; maturity | Distinguish complete zero, partial, unavailable and pending |
| Portfolio | Project; business goal; material issue; evidence; urgency; next step | Rights/project isolation; do not rank incompatible currencies or goals as one KPI |
| Decision history | Decision; user choice; confirmed effect; measurement state; conclusion; revisit | Preserve original evidence/version and uncertainty, not just latest status |

For a useful response, give the principal observation in prose, present the table supporting it, and offer the next relevant drill-down. This is a default, not a required template for every message. Numeric precision should reflect the source and decision; preserve fractional attributed conversions rather than rounding them into people.

Example of honest missingness (illustrative values, never live evidence): a campaign with spend 20,000 RUB, six form events and no linked CRM has cost per form 3,333.33 RUB, but unknown qualified lead count and unknown cost per qualified lead. It is not a zero-quality campaign.
