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

# Report requests obey configured range, filter, bucket, result and execution limits

Validated ranges, filters, property/event selections, timezones and buckets. Defaults: 3,660 days, 20 filters, 2,000 datapoints, 1,000 dimension results, eight concurrent reports and 30-second report deadline. These are implementation limits, not universal service guarantees.
