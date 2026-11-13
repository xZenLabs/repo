# v0.2.0.7 · 2026-11-13


- Switched opt-in KOReader Reading Statistics uploads to CrossPoint's per-book `POST /api/v1/stats/koreader` protocol for compatible CrossPoint and Techy-Notes servers, replacing the former Techy-Notes event endpoint.
- Preserved ordinary KOSync progress-only compatibility. Enhanced-capability responses gate uploads; servers without a capabilities endpoint may be probed only with explicit statistics consent, and missing statistics endpoints are remembered until an explicit recheck.
- Added per-server IANA reading time zones, full-history first upload, per-book change fingerprints, strict server acknowledgments, record/body limits, and safe handling of duplicate/updated page records and HTTP 409 history conflicts.
- Reading statistics remain opt-in and never change reading positions or highlights.

# v0.2.0.6 · 2026-10-13


- Fixed false progress-sync failures on slower servers where LuaSec surfaced wantread after the previous 5-second background block timeout even though the server continued processing and returned HTTP 200.
- Increased only the forked background HTTP timeout budget to 30/60 seconds so slow enhanced-server progress and optional-data requests can complete without blocking the KOReader UI; the emergency synchronous fallback remains tightly bounded.
- Added transport regression coverage for a slow-but-successful response while preserving real wantread failures for normal retry handling.

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
