---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/events.rs"
    }
  ]
}
---

# Pageview

An admitted pageview occurrence, distinguished from custom events by its session timing and exit measurement. Raw client IP is not retained.

## Information kept

- **Entity ID** — The submitted source identifier; historical events may outlive its registered source.
- **Recorded at** — Normalized occurrence time; public events use receipt time and batches may supply bounded timestamps.
- **Visitor group** — An opaque derived group, scoped by source and rotating salt, or random when configured or metadata is absent.
- **Hostname** — Normalized hostname of the submitted URL.
- **Path** — URL path with query and fragment omitted.
- **Referrer** — Normalized supplied referrer after supported admission checks.
- **Platform** — Operating platform inferred from supplied user agent.
- **Browser** — Browser inferred from supplied user agent.
- **Mobile** — Mobile classification inferred from supplied user agent.
- **Country** — Country retained under the current location-detail policy.
- **City** — City retained only under city-detail policy and available location data.
- **Campaign attribution** — Recognized source, medium, campaign, term and content attribution stored separately from path.
- **Screen width** — Submitted or tracker-bucketed screen width.
- **Orientation** — Submitted portrait or landscape metadata when available.
- **Properties** — Limited string values from primitive custom properties; null is omitted and nested values are refused.
- **Pageview timing** — Previous and next Pageview timing for the same source and group; custom events do not form the links.
- **Exit time** — Monotonic eligible exit measurement, capped at 30 minutes after the Pageview.
