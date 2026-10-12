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
        "Username",
        "Local credential",
        "Administrator access"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "packages/web/src/components/settings/users/dialogs.tsx"
    }
  ]
}
---

# Users

Account discovery shows usernames and shipped roles. New local-account creation takes username, password and Administrator-access selection.
