---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/projects.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/reports/mod.rs"
    }
  ],
  "domain": "projects",
  "relations": [
    {
      "entity": "entity",
      "verb": "includes",
      "cardinality": "many-to-many"
    }
  ]
}
---

# Project

A named grouping of currently associated sources, with visibility and display policy and derived report results. Current membership determines which historical events contribute.

## Information kept

- **Project ID** — The immutable grouping identifier.
- **Name** — The subject’s editable display name.
- **Visibility** — Public, Unlisted, Internal or Private access policy, with enumeration distinct from direct access.
- **Entities** — Current source association.
- **Metric display** — Auto, Always or Hidden per supported metric; Auto resolves current source collection settings.
- **Dimension display** — Auto, Always or Hidden per supported dimension and custom-data display.
- **Report availability** — Derived hidden-metric, hidden-dimension and custom-event availability for current source settings and display policy.
- **Views** — Count of selected event occurrences in the requested half-open window.
- **Unique visitors** — Distinct visitor groups in the selected events; groups are not identified people.
- **Bounce rate** — Single-page entries divided by entries; summary null below the entry minimum and dimensions omitted below it.
- **Time on site** — Average measured Pageview duration, preferring a qualifying next Pageview over exit; summary null and dimensions omitted below the measurement minimum.
- **Current visitors** — Distinct groups in Pageviews recorded at or after now minus five minutes, independently of selected range, filters or custom event.
- **Comparison** — Difference against the immediately preceding equal-duration window.
- **Graph** — Timezone-aligned metric buckets, including empty buckets; bucket uniques need not sum to summary uniques.
- **Dimension breakdowns** — Ranked dimension aggregates after selected filters and configured result limits.
- **Bounce-rate breakdowns** — Entry and exit boundary aggregates, with dimension sample suppression.
- **Time-on-site breakdowns** — Measured-duration aggregates, with dimension sample suppression.
- **Custom-event breakdowns** — Ranked named event counts, including truncation information.
- **Property breakdowns** — Custom property keys or values; missing keys are omitted and keys can become filters.
- **Earliest event** — Earliest event across current source IDs, including all event types, used by All Time.
