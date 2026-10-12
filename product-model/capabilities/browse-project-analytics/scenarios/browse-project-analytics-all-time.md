---
{
  "kind": "edge",
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
      "text": "All Time is selected for an accessible grouping.",
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
      "text": "The Product reads the earliest retained occurrence across current sources and all event types to set the All Time boundary",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "project",
          "effect": "reads",
          "facts": [
            "Earliest event"
          ]
        }
      ],
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
        "p": {
          "place": "website::public::project"
        },
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
        }
      ],
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
        "p": {
          "place": "website::public::project"
        },
        "a": {
          "place": "website::account::project"
        }
      }
    },
    {
      "text": "The range starts at the local day of the earliest event across current sources and all event types, through the selected current day. An empty history uses the supported fallback; normal range limits still apply.",
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

# Browse Project analytics — all time

## Trigger

All Time is selected for an accessible grouping.

## Outcome

The range starts at the local day of the earliest event across current sources and all event types, through the selected current day. An empty history uses the supported fallback; normal range limits still apply.

## Edge cases

- Current visitors is a separate recent-Pageview group query; selected report dates, filters and custom-event name do not constrain it.
