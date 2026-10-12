---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "preview-pruning",
      "contexts": [
        {
          "place": "website::administration"
        },
        {
          "place": "liwan-cli"
        }
      ]
    },
    {
      "type": "capability",
      "id": "prune-events",
      "contexts": [
        {
          "place": "website::administration"
        },
        {
          "place": "liwan-cli"
        }
      ]
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

# Explicit pruning applies current registered-source retention and data-clearing policy

Registered-source retention deletion and clearing of disabled campaign/location/session data; no retrospective host/drop filtering or visitor regrouping; preview/application can differ; processing is not globally atomic. Only currently registered sources are iterated. Cutoff deletion is strict; campaign clearing removes all campaign fields, country detail clears city, no location clears country/city, and session-disabled policy clears previous/next/exit measurements. Removed-source history is not automatically pruned. Preview counts can overlap events later deleted; processing has no global transaction.
