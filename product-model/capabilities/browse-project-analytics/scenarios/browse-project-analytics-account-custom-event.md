---
{
  "kind": "primary",
  "routes": {
    "a": "A — project"
  },
  "steps": [
    {
      "text": "The User requests the selected report, metric, range, interval and supported filters",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "a": {
          "place": "website::account::project"
        }
      }
    },
    {
      "text": "An accessible grouping with visible named occurrences has a supported named-event selection.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "a": {
          "place": "website::account::project"
        }
      }
    },
    {
      "text": "The Product saves the selected browser metric, range and interval; a range change resets interval",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "dashboard-preferences",
          "effect": "changes",
          "facts": [
            "Selected metric",
            "Selected range",
            "Selected interval"
          ]
        }
      ],
      "contexts": {
        "a": {
          "place": "website::account::project"
        }
      }
    },
    {
      "text": "The Product resolves the selected Project metadata and current Entity association, reads matching event facts and returns the summary and comparison; the five-minute group count uses its independent recent-page query",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "project",
          "effect": "reads",
          "facts": [
            "Project ID",
            "Name",
            "Visibility",
            "Entities",
            "Report availability",
            "Views",
            "Unique visitors",
            "Bounce rate",
            "Time on site",
            "Current visitors",
            "Comparison"
          ]
        },
        {
          "entity": "entity",
          "effect": "reads",
          "facts": [
            "Entity ID",
            "Name"
          ]
        },
        {
          "entity": "custom-event",
          "effect": "reads",
          "facts": [
            "Entity ID",
            "Recorded at",
            "Visitor group",
            "Hostname",
            "Path",
            "Referrer",
            "Platform",
            "Browser",
            "Mobile",
            "Country",
            "City",
            "Campaign attribution",
            "Screen width",
            "Orientation",
            "Properties",
            "Event name"
          ]
        },
        {
          "entity": "pageview",
          "effect": "reads",
          "facts": [
            "Entity ID",
            "Recorded at",
            "Visitor group"
          ]
        }
      ],
      "contexts": {
        "a": {
          "place": "website::account::project"
        }
      }
    },
    {
      "text": "The Product returns the requested visible metric’s timezone-aligned graph, filling missing buckets with zero",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "project",
          "effect": "reads",
          "facts": [
            "Graph"
          ]
        }
      ],
      "contexts": {
        "a": {
          "place": "website::account::project"
        }
      }
    },
    {
      "text": "The Product returns supported visible dimension and property aggregates for the selected custom-event name",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "project",
          "effect": "reads",
          "facts": [
            "Dimension breakdowns",
            "Property breakdowns"
          ]
        }
      ],
      "contexts": {
        "a": {
          "place": "website::account::project"
        }
      }
    },
    {
      "text": "The Product returns ranked visible custom-event counts and truncation information",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "project",
          "effect": "reads",
          "facts": [
            "Custom-event breakdowns"
          ]
        }
      ],
      "contexts": {
        "a": {
          "place": "website::account::project"
        }
      }
    },
    {
      "text": "Counts, uniques, graph and property/dimension results reflect the selected event name. page occurrence-only session measurements are not synthesized for named events.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
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

# Browse Project analytics — account custom event

## Trigger

An accessible grouping with visible custom events has a supported named-event selection.

## Outcome

Counts, uniques, graph and property/dimension results reflect the selected event name. Pageview-only session measurements are not synthesized for custom events.

## Edge cases

- Current visitors is a separate recent-Pageview group query; selected report dates, filters and custom-event name do not constrain it.
