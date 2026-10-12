---
{
  "availability": [
    {
      "place": "website::administration"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/external_auth.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/external_auth/mod.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "packages/web/src/components/settings/auth/index.tsx"
    }
  ],
  "domain": "authentication"
}
---

# Add Team mapping

One group-to-Team mapping is added within the configured limit, used only for newly created external accounts.

