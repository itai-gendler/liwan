---
{
  "kind": "validation",
  "routes": {
    "p": "P — project",
    "a": "A — project"
  },
  "steps": [
    {
      "text": "The User requests the selected report, metric, range, interval and supported filters",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "website::public::project"
        },
        "a": {
          "place": "website::account::project"
        }
      }
    },
    {
      "text": "A specifically requested graph/dimension/named occurrence selection is explicitly hidden or incompatible with supported event measurements.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "p": {
          "place": "website::public::project"
        },
        "a": {
          "place": "website::account::project"
        }
      }
    },
    {
      "text": "That request is rejected instead of returning the hidden or unsupported selected result. Summary Views/uniques and filters on hidden dimensions are not implied to be universally suppressed.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "website::public::project"
        },
        "a": {
          "place": "website::account::project"
        }
      }
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/reports/mod.rs"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "packages/web/src/components/dashboard/project/index.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "packages/web/src/components/dashboard/projects/index.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "packages/web/src/api/ranges.ts"
    }
  ]
}
---

# Browse Project analytics — hidden or unsupported selection

## Trigger

A specifically requested graph/dimension/custom-event selection is explicitly hidden or incompatible with supported event measurements.

## Outcome

That request is rejected instead of returning the hidden or unsupported selected result. Summary Views/uniques and filters on hidden dimensions are not implied to be universally suppressed.

## Edge cases

- Current visitors is a separate recent-Pageview group query; selected report dates, filters and custom-event name do not constrain it.
