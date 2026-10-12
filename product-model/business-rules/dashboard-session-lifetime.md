---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "sign-in",
      "contexts": [
        {
          "place": "website::public"
        }
      ]
    },
    {
      "type": "capability",
      "id": "sign-out",
      "contexts": [
        {
          "place": "website::account"
        },
        {
          "place": "website::administration"
        }
      ]
    },
    {
      "type": "capability",
      "id": "view-my-account",
      "contexts": [
        {
          "place": "website::account"
        }
      ]
    },
    {
      "type": "capability",
      "id": "revoke-sessions",
      "contexts": [
        {
          "place": "website::administration"
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
      "target": "crates/liwan/src/web/session.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/external_auth.rs"
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
    }
  ]
}
---

# Dashboard sign-ins expire without renewal and resolve the current Account role

Configured expiry without renewal; current role/access resolution; malformed cookie-pair handling. Logout expiry errors still permit browser-cookie clearance.
