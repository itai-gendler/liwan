---
{
  "entities": [
    {
      "entity": "authentication-settings",
      "shows": [
        "External sign-in enabled",
        "Provider"
      ]
    },
    {
      "entity": "openid-connect-registration",
      "shows": [
        "Sign-in label"
      ]
    },
    {
      "entity": "account",
      "collects": [
        "Username",
        "Local credential"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "packages/web/src/components/login/index.tsx"
    }
  ]
}
---

# Sign in

Local or saved-provider sign-in. Password proof and external flow proof are transient inputs.
