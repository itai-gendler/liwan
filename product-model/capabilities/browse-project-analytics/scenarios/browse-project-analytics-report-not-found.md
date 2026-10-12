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
      "text": "The grouping is absent or direct report access does not resolve.",
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
      "text": "The report is not found (404); no protected report facts are returned.",
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

# Browse Project analytics — report not found

## Trigger

The grouping is absent or direct report access does not resolve.

## Outcome

The report is not found (404); no protected report facts are returned.

## Edge cases

- Current visitors is a separate recent-Pageview group query; selected report dates, filters and custom-event name do not constrain it.
