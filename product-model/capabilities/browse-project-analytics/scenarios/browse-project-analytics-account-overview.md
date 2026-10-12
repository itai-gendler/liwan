---
{
  "kind": "primary",
  "routes": {
    "a": "A — projects"
  },
  "steps": [
    {
      "text": "The User requests the selected report, metric, range, interval and supported filters",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "a": {
          "place": "website::account::projects"
        }
      }
    },
    {
      "text": "An enumerable accessible grouping has admitted events.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "a": {
          "place": "website::account::projects"
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
          "place": "website::account::projects"
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
        "a": {
          "place": "website::account::projects"
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
          "place": "website::account::projects"
        }
      }
    },
    {
      "text": "Overview metrics and the selected metric’s graph reflect the current source set and browser range.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "a": {
          "place": "website::account::projects"
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

# Browse Project analytics — account overview

## Trigger

An enumerable accessible grouping has admitted events.

## Outcome

Overview metrics and the selected metric’s graph reflect the current source set and browser range.

## Edge cases

- Current visitors is a separate recent-Pageview group query; selected report dates, filters and custom-event name do not constrain it.
