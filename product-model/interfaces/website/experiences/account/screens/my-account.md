---
{
  "entities": [
    {
      "entity": "account",
      "shows": [
        "Username",
        "Administrator access"
      ],
      "collects": [
        "Local credential"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "packages/web/src/components/settings/me/index.tsx"
    }
  ]
}
---

# My account

The selected own account and password-change process, including current-password proof and confirmation.
