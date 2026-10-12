---
{
  "kind": "primary",
  "routes": {
    "p": "P — project"
  },
  "steps": [
    {
      "text": "The Visitor requests the selected report, metric, range, interval and supported filters",
      "kind": "actor",
      "actor": "visitor",
      "entities": [],
      "contexts": {
        "p": {
          "place": "website::public::project"
        }
      }
    },
    {
      "text": "A directly accessible grouping and page occurrence selection are requested.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "p": {
          "place": "website::public::project"
        }
      }
    },
    {
      "text": "The Product saves the selected browser metric, range and interval; a range change resets interval",
      "kind": "product",
      "actor": "visitor",
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
        "p": {
          "place": "website::public::project"
        }
      }
    },
    {
      "text": "The Product resolves the selected Project metadata and current Entity association, reads matching event facts and returns the summary and comparison; the five-minute group count uses its independent recent-page query",
      "kind": "product",
      "actor": "visitor",
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
          "entity": "pageview",
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
            "Pageview timing",
            "Exit time"
          ]
        }
      ],
      "contexts": {
        "p": {
          "place": "website::public::project"
        }
      }
    },
    {
      "text": "The Product returns the requested visible metric’s timezone-aligned graph, filling missing buckets with zero",
      "kind": "product",
      "actor": "visitor",
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
        "p": {
          "place": "website::public::project"
        }
      }
    },
    {
      "text": "The Product returns supported visible dimension and property aggregates for selected page occurrences",
      "kind": "product",
      "actor": "visitor",
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
        "p": {
          "place": "website::public::project"
        }
      }
    },
    {
      "text": "The Product returns the available bounce-rate and measured-duration breakdowns; undersampled groups are omitted",
      "kind": "product",
      "actor": "visitor",
      "entities": [
        {
          "entity": "project",
          "effect": "reads",
          "facts": [
            "Bounce-rate breakdowns",
            "Time-on-site breakdowns"
          ]
        }
      ],
      "contexts": {
        "p": {
          "place": "website::public::project"
        }
      }
    },
    {
      "text": "Views, uniques, supported session metrics, graph, dimensions and property results reflect selected page occurrences, half-open dates and AND filters.",
      "kind": "product",
      "actor": "visitor",
      "entities": [],
      "contexts": {
        "p": {
          "place": "website::public::project"
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

# Browse Project analytics — public pageviews

## Trigger

A directly accessible grouping and Pageview selection are requested.

## Outcome

Views, uniques, supported session metrics, graph, dimensions and property results reflect selected Pageviews, half-open dates and AND filters.

## Edge cases

- Current visitors is a separate recent-Pageview group query; selected report dates, filters and custom-event name do not constrain it.
