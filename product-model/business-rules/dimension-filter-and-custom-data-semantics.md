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

# Report filters combine with AND and breakdowns rank and limit selected aggregates

AND filters; LIKE-style matching/wildcards; entry/exit boundary selection; custom-event/property exclusions, result limits and ranking; unsupported combinations may fail during execution. Dimension queries rank and limit results; bounce ranks ascending and other metrics descending. UI searching only searches returned values. Entry/exit URL breakdowns use boundary Pageviews, not every Pageview in the session. City selection strips the displayed country prefix without adding a country predicate. Unknown values map to null filters. Equal-style ILIKE/LIKE matching can preserve wildcard semantics. Property-key selection filters presence; property-value queries omit missing keys.
