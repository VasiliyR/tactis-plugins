# Exact retained evidence

Metrika query-version 2 receipts use explicit `cross_device_last_significant` dimensions, filters and attribution. The domain label `LASTSIGN` denotes this last-significant-source observation; it is separate from Direct `AUTO`. Earlier receipts remain history and do not prove the corrected model. Preserve `metrika_attribution_model_unproven` and request new collection only when the question requires it.

Use a known exact locator directly. Read only the section needed by the question; a saved publication remains historical and every reader checks current authorized scope.

## Wordstat demand

For a search-demand question, reuse a relevant exact `get_demand_publication`, or
call `acquire_demand` for one to fifty exact phrases with the known project,
optional account, regions and devices. Tactis can provide service-managed
Wordstat access: a configured service card requires no customer Cloud account,
folder ID, API key or repeated Direct OAuth. Capture itself checks current
authority; do not add a mandatory connector-status preflight. Own account or
project keys retain their actual precedence, and an explicit revoked connection
cannot be bypassed with service access or another account.
After an explicit disconnect, the human manager can choose **Использовать доступ
Tactis** in the same source settings to restore service access without Cloud
credentials. A capture never clears revocation or switches their own selected key.

Use `acquire_demand_dynamics` for separate calendar history with explicit dates
and supported daily, weekly or monthly buckets. Every new request, including a
single phrase, admits one durable batch to the existing data worker without
waiting for provider reads. Keep its command key and exact
inputs on replay. Read the returned batch id with `get_demand_publication` after
both `next_due_at` and `retry_after_seconds` (five seconds for short commands,
thirty for larger batches while pending). A lost response or a concurrent retry
reuses that accepted command; never submit another key to work around a timeout.
Exact replay of an older immutable publication can return that publication directly,
or an exact JSON chunk whose `next` continues with `get_demand_publication`.
Do not poll unchanged progress repeatedly or submit a replacement batch.
The reader returns useful phrase counts or all calendar points/coverage, with
whole-phrase pagination via `next_offset`; read the required pages, not fifty
child publications. If a phrase would exceed the complete host display budget,
its item explicitly has `response_omitted=true`: supplied totals/coverage are a
projection, not the unread rows or calendar points. Follow that item's
`read_original` only when the omitted evidence is needed. The same
`get_demand_publication` reads the immutable child as ordinary exact JSON chunks:
follow returned `next` arguments with `body_offset` and `wire_sha256`, concatenate
the fragments unchanged and verify the final wire hash before claiming a full
original. The wire hash is separate from the retained publication fingerprint.
Large immutable reads can return a chunk immediately. Unread rows stay unknown;
no new capture, Work or connector setup is needed to read them.
`publication_id` and `publication_fingerprint` on each item
are its immutable origins. Use selected child origins in Work foundation refs,
`preview_demand_scenario` or `get_page_growth_evidence`; a batch id carries
continuation, not measured single-phrase evidence. Saving Work is not required
to continue a known batch id.

Each worker step reads one phrase with current rights and credentials. The
finite batch bounds cost to at most two HTTP attempts per phrase and expires
after two hours. Wordstat's default provider quota is shared across customers;
the fifty-phrase cap does not reserve quota. Rate/auth/setup denial stops the
remaining phrases with zero attempts. An interrupted in-flight read without a
saved receipt is unavailable, not silently repeated as another billable read.
Already saved receipts survive restarts, revocation and restore. Offline restore
stops pending batches with `backup_restore`; it never resumes paid service reads.
A retained publication
is immutable. Missing buckets and failed
phrases remain unknown. `search_api_operator_setup_required` and
`search_api_operator_authorization_denied` belong to Tactis configuration; report
that limitation and continue the useful supported work instead of asking the
client to create Cloud credentials. Respect `retry_after_seconds` after provider
rate limiting; an unchanged denied source does not justify repeated capture.

Trailing-30-day counts and calendar history have different source windows.
Counts measure search queries, not unique people, ad impressions, buyers or
sales. Do not sum overlapping phrases as market size. A scenario uses explicit
CTR/CR/CPC assumptions and one complete trailing-30-day phrase; calendar history
does not substitute for that input or establish causal seasonality.

## Retained statistics and coverage

`get_current_daygrain(profile="campaign_primitives")` locates the separate automatic spend/clicks/impressions publication for 60 completed Moscow days. `profile="full_rolling"` locates the full daily diagnostic publication, whose calendar and observation times are separate. These locators and a newly saved Analysis, Matrix, Dossier or latest goal observation do not establish current source freshness. Use their exact retained readers for history and reproducibility. For `get_campaign_metrics`, always pass `project_id`, the exact **Daygrain** `publication_id`, `start` and `end`; select family and exact counter/goal arguments; the MCP derives Direct or Metrika from family. Configuration/Analysis IDs cannot substitute for Daygrain. Inspect further receipts only for a relevant gap or decision.

For weekly charts, use `get_campaign_metrics(aggregation="calendar_week")` over the exact retained window, once per needed source/family and exact counter/goal pair. Weeks are Monday–Sunday in Europe/Moscow, clipped to the requested dates; keep the first/last partial weeks labelled. Start with an explicit small `limit` such as 5 and follow `next_offset`: pagination counts campaign-week rows in frozen campaign order, then chronological week order. Preserve each row's period, expected days, metric coverage, currency and VAT basis. A page is not the whole account; the server response budget does not guarantee that the host will display a large page. Omitted/"total" aggregation retains the existing exact-window totals.

For search-query period totals, use `get_campaign_metrics(family="search_query", aggregation="total")` on the exact Daygrain publication and dates. It returns spend-ranked campaign/query rows and a full selected-scope `summary` with totals, row count and campaign-day coverage, including on a short first page. A shortlist needs only enough ranked candidates for the decision; a complete denominator does not require reading every page or daily fact. Keep `metrics=null` as unknown; `observed_metrics` may be partial. These totals cover retained search-query rows, not necessarily all campaign spend/clicks. A matching existing Dossier remains useful for richer criterion observations; preparing another Analysis/Dossier is unnecessary for these totals.

For geography, demographics or device period totals, use the same reader with `family="geography"`, `"demographics"` or `"device"` and `aggregation="total"`. It groups the full selected campaign scope by location ID, full gender/age pair or exact device value. The typed `dimension_totals` page includes the full summary, campaign count/fingerprint and campaign-day coverage; the page itself contains only the ranked dimensions returned. Keep native identities, geographic label consensus/variant counts and the `retained_<family>_rows` population. Unknown identities and provider placeholders differ. Null totals remain unknown; incompatible campaign goal/counter pairs leave both row and summary conversions unknown. A city absent from a short page is not proven absent from the publication. Read another page when needed for that observation, not to recalculate the full summary. Daily facts or a new Analysis/Dossier are unnecessary for these totals. Other leaf families and hourly-data limitations retain their existing routes.

To explain missing data, call `get_daygrain_manifest(include_coverage=true)` with the same exact Daygrain ID and, when relevant, paired `start`/`end` dates. Page the small coverage groups using `coverage_limit`/`coverage_offset`; compare the exact family/counter/goal/attribution group needed for the decision. The dates filter receipt `source_date`, not a diagnostic's whole affected window. Keep the original retained publication's partial state, catalog omissions, sampling/suppression and omitted error counts visible even when the selected metric is complete. Drill into `get_daygrain_receipts(covered=false, family=...)`, optionally with the exact counter/goal and paired dates, only for relevant uncovered receipts; filters apply before paging. Omit unused selectors rather than sending null. Complete campaign spend/goal coverage does not repair missing ad-level attribution or establish revenue.

Read `get_current_daygrain`, then pin the statistics publication. Read `get_daygrain_receipts` when needed to explain a coverage gap or establish the decision's exact calendar, counter/goal, attribution, sampling or provider-failure basis. `get_daygrain_values` exposes daily facts; `get_campaign_metrics` takes that exact Daygrain publication_id, not an Analysis/Dossier/Candidate ID, and exposes campaign totals for an exact window and compatible source family. Follow pages when claiming a full account view. Null totals mean incomplete metric/day coverage; zero requires complete source evidence. A known zero in one campaign does not fill unknown queries, placements or another goal.

Keep Direct AUTO and Metrika LASTSIGN definitions explicit. Never combine different events, currencies, VAT bases, calendars or attribution definitions as one comparable CPA/ROAS. Traffic/spend facts remain useful when business-goal meaning is unknown; business success and qualified leads require their own evidence. Revenue and a confirmed conversion-value estimate are different quantities.

## When more evidence is actually needed

A required new annual archive follows [historical acquisition](source-inventory.md#longer-historical-acquisition); use an existing compatible retained publication first. Exact Analysis/Dossier/native membership or Configuration identity uses [proof readers](source-proof.md). A known publication ID needs no discovery round trip. Several independent pinned reads can use [the bounded bundle](source-proof.md#bundle-pinned-reads). Do not load these branches for ordinary totals/chart labels.

Preserve the original source period, scope, timezone, event/attribution, currency/VAT, as-of and partial coverage. A read has current authorized scope; an old basis for a new action cannot silently be replaced with latest. Direct/Metrika/CRM joins use [the matrix](marketing-data-matrix.md) only when the question calls for them.
