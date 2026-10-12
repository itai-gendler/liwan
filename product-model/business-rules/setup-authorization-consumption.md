---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "installation-settings",
      "effect": "changes",
      "facts": [
        "Setup availability"
      ],
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

# Visitors consume available setup only after successful initial Account creation

Setup availability must be true. Successful initial Account creation consumes that same process-held setting; refused proof or failed creation does not consume it.
