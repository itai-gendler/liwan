---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "browse-projects",
      "contexts": [
        {
          "place": "website::public"
        },
        {
          "place": "website::account"
        }
      ]
    },
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

# Graph and custom-event refresh depend on range and change formatting follows the metric

Inspected range-dependent graph/custom-event polling, without summary/dimension polling parity; bounce change uses percentage points; other positive-current/zero-previous change uses sentinel −1 rendered `∞`. The formatter also renders any exact −1 input as `∞`. Graphs/custom-event results poll every minute for ranges including today and otherwise use ten-minute stale behavior; no equivalent summary/dimension polling is asserted. Other metric change is (current − previous)/previous × 100 when the previous value is nonzero, with the implemented positive-current/zero-previous −1 sentinel rendered as infinity.
