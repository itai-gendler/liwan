---
{
  "availability": [
    {
      "place": "website::account"
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
    }
  ],
  "domain": "my-account"
}
---

# Change password

The local credential is replaced using guarded comparison, other sign-ins are revoked, and the current sign-in is retained.

