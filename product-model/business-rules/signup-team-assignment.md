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

# Default and mapped Teams are assigned only when an external Account is first created

Assign default/mapped Teams to newly created external Accounts only; no continuous synchronization of existing identities.
