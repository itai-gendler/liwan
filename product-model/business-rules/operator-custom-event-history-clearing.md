---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "custom-event",
      "effect": "changes",
      "facts": [
        "Campaign attribution",
        "Country",
        "City"
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

# Only Operators clear retained custom-event campaign and location facts through Liwan CLI

Explicit CLI pruning clears disabled campaign and location facts under current registered-source policy; custom events have no Pageview session measurements.
