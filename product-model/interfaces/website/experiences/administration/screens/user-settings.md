---
{
  "entities": [
    {
      "entity": "account",
      "shows": [
        "Username",
        "Administrator access",
        "Teams"
      ],
      "collects": [
        "Administrator access",
        "Teams"
      ]
    },
    {
      "entity": "team",
      "shows": [
        "Team ID",
        "Name"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "packages/web/src/components/settings/users/index.tsx"
    }
  ]
}
---

# User settings

One Account’s Administrator access and Team memberships, plus the operation to revoke all its sign-ins. The page does not retrieve a session inventory.
