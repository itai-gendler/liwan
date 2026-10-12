---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "openid-connect-registration",
      "effect": "reads",
      "facts": [
        "Sign-in label"
      ],
      "contexts": [
        {
          "place": "website::public::sign-in"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "visitor",
        "user",
        "administrator"
      ],
      "when": [
        {
          "entity": "authentication-settings",
          "fact": "External sign-in enabled",
          "is": true
        },
        {
          "entity": "authentication-settings",
          "fact": "Provider",
          "is": "OpenID Connect"
        },
        {
          "entity": "installation-settings",
          "fact": "Setup availability",
          "is": false
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

# Visitors and unsigned roleholders read the OpenID Connect label only when that provider is enabled

The saved singleton Authentication settings must enable external sign-in and select OpenID Connect; initial setup must be complete, and only its public Sign-in label is disclosed here.
