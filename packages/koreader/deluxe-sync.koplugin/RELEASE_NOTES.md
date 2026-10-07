# v0.2.0.5 · 2026-10-07


- Fixed enhanced device registration to advertise **Vocabulary Builder** support. Vocabulary synchronization and its data-sharing/server-capability checks already worked in 0.2.0.4; this corrects the client capability heartbeat so compatible servers can accurately show Vocabulary Builder in the device capability list.
- Standard KOSync behavior and existing per-server Vocabulary Builder / Vocabulary Reading Context sharing choices are unchanged.
- Clarified server setup and editing: new servers now expose an explicit **Save** action, saves show immediate transient progress feedback, and every successful save automatically signs in and refreshes server capabilities. The manual **Authenticate / Sign in** action remains available for an explicit credential/capability recheck and now explains that the capability probe is running.

# v0.2.0.4 · 2026-09-29


- Added first-class KOReader completion feedback synchronization for supported enhanced servers, including half-star ratings and the private completion review Note.
- Added an explicit per-server **Ratings & Reviews** sharing control that is fail-closed for existing servers and rechecked before queued/retried sends.
- Added capability-gated progress event timestamps for enhanced servers so delayed progress can be ordered by when the reading position was captured instead of when the request finally reaches the server.
- Preserved the original progress event time through offline queues, failed online sends, metadata fallback, and manual/automatic retries. Retry now resolves an unknown timestamp capability before delivery, preventing reconnect races from making stale queued progress look newer.
- Preserved compatibility with ordinary KOSync servers: `event_timestamp` is sent only after explicit capability confirmation, while unsupported servers continue using the standard progress payload.
- Preserved feedback privacy and backward compatibility: unsupported servers receive no rating/review fields, and ordinary KOSync behavior is unchanged.

# v0.2.0.3 · 2026-09-20


- Fixed annotation synchronization getting permanently blocked when the client remembered a revision for an annotation the server no longer knew. Deluxe-Sync now repairs that stale state, retries the affected annotation from revision zero, and continues uploading newer highlights, notes, and bookmarks instead of failing the whole batch with HTTP 422.
- Added a debounced `AnnotationsModified` hook so newly created or edited KOReader annotations are pushed promptly rather than waiting for a later progress-sync lifecycle event.
- Suppressed the plugin's own `AnnotationsModified` notification during remote annotation application so server updates do not create an upload feedback loop.
- Preserved the last confirmed enhanced-server capability set across transient capability-request failures, while still clearing capabilities for definitive unsupported responses.
- Added clearer annotation-sync diagnostic logging for sharing-disabled, capability-unavailable, offline, in-flight, and stale-revision recovery paths.

# v0.2.0.2 · 2026-09-16


- Added KOReader book series metadata to the existing Book Metadata payload for compatible servers. Deluxe-Sync now sends series and numeric series_index values when KOReader exposes them.
- Saved KOReader doc_props remain authoritative, with document properties used as a fallback. Zero and decimal series indexes are preserved, while invalid indexes are omitted.
- Existing Book Metadata consent, capability checks, retry sanitization, and standard KOSync compatibility remain unchanged; unsupported servers do not receive the new metadata fields.
- Refreshed the README capability summary to document Vocabulary Builder synchronization and the current per-server data-sharing controls.

# v0.2.0.1 · 2026-09-14


- Added conservative ASIN extraction from KOReader document metadata. Explicitly labeled `asin`, `mobi-asin`, and Amazon-ASIN forms are normalized to uppercase and included in the existing Book Metadata payload for compatible servers.
- Unlabeled 10-character identifiers are never guessed to be ASINs, preventing ISBN-10 values from being misclassified.
- Existing Book Metadata consent, metadata compatibility fallback, and ordinary KOSync behavior remain unchanged.
- Restored the intended enhanced-server client notice flow so compatible servers can surface actionable account or linked-service warnings on the reader, keep an attention marker on affected server entries, and suppress repeated display of the same notice for 24 hours.
- Fixed Authenticate / Sign in capability refresh so the complete enhanced capability set is cached through the shared path; client notices and future enhanced capabilities are no longer skipped by the server test flow.
- Progress pushes now allow a longer asynchronous response window before declaring a compatible server unavailable, preventing slower successful writes from being queued as false failures while keeping the tight synchronous fallback bounded.
- Manual queued-update retry status now closes before the refreshed queue result is shown, so the retry message no longer remains over the result.
