---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "change-password",
      "contexts": [
        {
          "place": "website::account"
        }
      ]
    },
    {
      "type": "capability",
      "id": "reset-user-password",
      "contexts": [
        {
          "place": "liwan-cli"
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
      "target": "packages/web/src/components/settings/me/index.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/admin.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/users.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/cli.rs"
    }
  ]
}
---

# Guarded own-password replacement revokes other sign-ins and CLI reset revokes all

Guarded replacement prevents concurrent overwrite; own change preserves the current session and revokes others; CLI reset omits old-password/current-session proof and revokes sessions.
