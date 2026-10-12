---
{
  "kind": "edge",
  "routes": {
    "c": "C"
  },
  "steps": [
    {
      "text": "The Operator requests application of current retention and disabled-data policy",
      "kind": "actor",
      "actor": "operator",
      "entities": [],
      "contexts": {
        "c": {
          "place": "liwan-cli"
        }
      }
    },
    {
      "text": "Explicit pruning fails after some registered sources have been processed.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "c": {
          "place": "liwan-cli"
        }
      }
    },
    {
      "text": "Failure is exposed without claiming a global rollback; already completed source deletions/clearings can remain and later source processing need not have happened.",
      "kind": "product",
      "actor": "operator",
      "entities": [
        {
          "entity": "pageview",
          "effect": "removes"
        },
        {
          "entity": "custom-event",
          "effect": "removes"
        }
      ],
      "contexts": {
        "c": {
          "place": "liwan-cli"
        }
      }
    },
    {
      "text": "The Product changes the selected Pageview; changes the selected named occurrence",
      "kind": "product",
      "actor": "operator",
      "entities": [
        {
          "entity": "pageview",
          "effect": "changes",
          "facts": [
            "Campaign attribution",
            "Country",
            "City",
            "Pageview timing",
            "Exit time"
          ]
        },
        {
          "entity": "custom-event",
          "effect": "changes",
          "facts": [
            "Campaign attribution",
            "Country",
            "City"
          ]
        }
      ],
      "contexts": {
        "c": {
          "place": "liwan-cli"
        }
      }
    },
    {
      "text": "Failure is exposed without claiming a global rollback; already completed source deletions/clearings can remain and later source processing need not have happened.",
      "kind": "product",
      "actor": "operator",
      "entities": [],
      "contexts": {
        "c": {
          "place": "liwan-cli"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/admin.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/events.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/cli.rs"
    }
  ]
}
---

# Prune events — partial processing failure — cli

## Trigger

Explicit pruning fails after some registered sources have been processed.

## Outcome

Failure is exposed without claiming a global rollback; already completed source deletions/clearings can remain and later source processing need not have happened.
