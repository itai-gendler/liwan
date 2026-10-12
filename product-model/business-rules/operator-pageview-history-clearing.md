---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "pageview",
      "effect": "changes",
      "facts": [
        "Campaign attribution",
        "Country",
        "City",
        "Pageview timing",
        "Exit time"
      ],
      "contexts": [
        {
          "place": "liwan-cli"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "operator"
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
      "target": "crates/liwan/src/cli.rs"
    }
  ]
}
---

# Only Operators clear retained Pageview campaign, location and session facts through Liwan CLI

Explicit CLI pruning clears disabled campaign, location and Pageview session measurements under current registered-source policy.
