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
          "place": "website::administration"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "administrator"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/admin.rs"
    }
  ]
}
---

# Only Administrators clear retained Pageview campaign, location and session facts through Website administration

Explicit Website pruning clears disabled campaign, location and Pageview session measurements under current registered-source policy.
