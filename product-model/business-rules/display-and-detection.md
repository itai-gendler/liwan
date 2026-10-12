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
      "target": "crates/liwan/src/web/routes/dashboard.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/projects.rs"
    }
  ]
}
---

# Auto display resolves current collection compatibility and retained custom-data detection

Auto uses current source settings and historical custom-data detection; Always can expose partial data; Hidden is not blanket suppression of every response; cached detection can survive pruning. Auto can suppress session metrics under incompatible source grouping/session policy and campaign/location breakdowns under disabled collection. Historical custom-event/property detection can remain cached after pruning. Explicit Hidden blocks selected graph/dimension/custom-event requests but does not universally suppress summary Views/uniques or hidden-dimension filters.
