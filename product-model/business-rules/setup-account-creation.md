---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "creates",
      "contexts": [
        {
          "place": "website::public::setup"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "visitor"
      ],
      "when": [
        {
          "entity": "installation-settings",
          "fact": "Setup availability",
          "is": true
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/auth.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/users.rs"
    }
  ]
}
---

# Visitors create the first Administrator Account only while setup is available

Setup availability must be true in the installation’s process-held settings. Token and credential proof are separately validated before the initial Account is created with Administrator access.
