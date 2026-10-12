---
{
  "kind": "primary",
  "routes": {
    "b": "B"
  },
  "steps": [
    {
      "text": "The Tracker submits the latest tracked page’s exit signal",
      "kind": "actor",
      "actor": "tracker",
      "entities": [],
      "contexts": {
        "b": {
          "place": "event-ingestion::public-collection"
        }
      }
    },
    {
      "text": "Session collection and grouping/metadata permit a matching existing page occurrence with eligible following-page timing.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "b": {
          "place": "event-ingestion::public-collection"
        }
      }
    },
    {
      "text": "After asynchronous processing, the latest matching source/group/page Pageview gains a monotonic exit measurement capped at 30 minutes. No additional counted event is created.",
      "kind": "product",
      "actor": "tracker",
      "entities": [
        {
          "entity": "pageview",
          "effect": "changes",
          "facts": [
            "Exit time"
          ]
        }
      ],
      "contexts": {
        "b": {
          "place": "event-ingestion::public-collection"
        }
      }
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "packages/tracker/src/script.ts"
    }
  ]
}
---

# Record Pageview exit — qualifying update

## Trigger

Session collection and grouping/metadata permit a matching existing Pageview with eligible following-page timing.

## Outcome

After asynchronous processing, the latest matching source/group/page Pageview gains a monotonic exit measurement capped at 30 minutes. No additional counted event is created.
