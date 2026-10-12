---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "browse-project-analytics",
      "contexts": [
        {
          "place": "website::public"
        },
        {
          "place": "website::account"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/reports/shared.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/reports/stats.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/reports/graph.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/reports/dimension.rs"
    }
  ]
}
---

# Views count occurrences, uniques count groups and session metrics use measured Pageviews

Views count selected occurrences; uniques count distinct groups; session gaps exceed 30 minutes; bounce rate is one-Pageview entries divided by entries; duration averages measured Pageviews, preferring qualifying next-Pageview intervals over exit duration. A session gap exceeds 30 minutes. Entry Pageviews lack a previous Pageview within that bound; a single-page entry lacks a next one within it. Duration samples prefer next-Pageview gaps within the bound, otherwise qualifying exit gaps. Current visitors independently counts distinct Pageview groups with recorded time at least now minus five minutes across current sources; no selected filters/range or upper timestamp bound is added.
