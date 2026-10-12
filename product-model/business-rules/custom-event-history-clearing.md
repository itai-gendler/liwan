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

# Only Administrators clear retained custom-event campaign and location facts through Website administration

Explicit Website pruning clears disabled campaign and location facts under current registered-source policy; custom events have no Pageview session measurements.
