---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "pageview",
      "effect": "changes",
      "facts": [
        "Exit time"
      ],
      "contexts": [
        {
          "place": "event-ingestion::public-collection"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "tracker"
      ],
      "configuredBy": "entity",
      "when": [
        {
          "entity": "entity",
          "fact": "Session collection",
          "is": true
        }
      ]
    },
    {
      "actors": [
        "tracker"
      ],
      "configuredBy": "entity",
      "when": [
        {
          "entity": "entity",
          "fact": "Session collection",
          "absent": true
        },
        {
          "entity": "collection-settings",
          "fact": "Session collection",
          "is": true
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/event.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/events.rs"
    }
  ]
}
---

# Enabled effective session collection admits Pageview exits

Pageview changes Exit time. Effective Session collection enabled; matching and measurement eligibility remain derivations. The configuredBy Entity is the submitted source ID’s resolved collection policy. Its effective Session collection must be enabled. Random grouping, absent required metadata and missing/ineligible matches still derive ignored exits rather than successful measurements; no Pageview is created.
