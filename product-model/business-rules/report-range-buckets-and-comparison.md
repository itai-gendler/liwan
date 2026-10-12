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

# Report windows are half-open and graph buckets follow selected timezone boundaries

Start-inclusive/end-exclusive windows; immediately preceding equal-duration comparison; timezone-aligned buckets, Monday weeks and empty buckets; bucket uniques need not sum to summary uniques. Daily/week/month boundaries use the selected timezone; weeks begin Monday. Ambiguous local boundaries choose the earlier instant and nonexistent times advance to a usable minute. Local bucket starts can precede the requested start, but counted events obey the requested window. Missing buckets are filled with zero.
