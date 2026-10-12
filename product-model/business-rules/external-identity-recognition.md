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
    }
  ]
}
---

# External sign-in resolves the provider identity binding rather than merging by name or email

Binding by provider/issuer and subject; no automatic local-account merge by email/username.
