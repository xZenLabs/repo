# v1.1.0 · 2026-11-07

### Timezone support
- Events with a `TZID` are now converted to the device's local time instead of being shown at their literal wall-clock value.
- Embedded `VTIMEZONE` definitions are parsed (STANDARD/DAYLIGHT, `RDATE`, yearly `BYMONTH`/`BYDAY`/`BYMONTHDAY` transition rules, as exported by Google Calendar). When a feed omits them, the device's zoneinfo database is used if available.
- Recurring events keep their source-timezone wall-clock time across DST changes; `EXDATE`, `RECURRENCE-ID` and `UNTIL` honor the event's timezone.
- UTC (`...Z`) values no longer depend on the device's current DST state.
- An unresolvable `TZID` raises an explicit error rather than silently showing the wrong time. Date-only and floating times are unchanged (local).

### Week view
- The week view now uses a card grid: two columns in portrait, three in landscape, with the last day spanning the final row. Today is drawn with a heavier border; empty days show "No events".

### Navigation
- Physical page-turn buttons move to the previous/next period in the viewer.

### Thanks
- @alexcmx — timezone support (#3), week view table layout (#4)
- @WuInTime — page-turn button navigation (#2)

# v1.0.1 · 2026-08-04

- Fix all-day events leaking into the next day in DST-observing zones

    ICS.parseDateTime and the RRULE UNTIL parser forced isdst=false when
    building timestamps for date-only and floating date-time values. In a
    DST-observing timezone (e.g. Europe/Lisbon in August), this shifts the
    resulting epoch by the DST offset, pushing an all-day DTEND an hour
    past the following midnight and causing it to overlap that next day's
    bucket in groupByDay. Leave isdst unset so mktime auto-detects DST,
    matching the convention already used in calendar_view.lua's midnight()/
    addDays().

# v1.0.0 · 2026-07-10

 - initial release
