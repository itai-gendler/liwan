---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "team-mapping",
      "effect": "changes",
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
      ],
      "when": [
        {
          "entity": "authentication-settings",
          "fact": "Provider",
          "is": "OpenID Connect"
        }
      ]
    },
    {
      "actors": [
        "administrator"
      ],
      "when": [
        {
          "entity": "authentication-settings",
          "fact": "Provider",
          "is": "Microsoft"
        }
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

# Team mapping changes require the Administrator

Team mapping changes Group value/Team. Admin under a provider supporting mappings.
