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
      "target": "crates/liwan/src/web/routes/admin.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/api_keys.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "packages/web/src/components/settings/api-keys.tsx"
    }
  ],
  "domain": "api-keys"
}
---

# Regenerate API Key

The credential is replaced and its new secret revealed once. Expiry is reset and last use is cleared; original creation time is retained; scope and permission remain and the old credential stops authenticating.
