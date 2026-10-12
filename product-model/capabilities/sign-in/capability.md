---
{
  "availability": [
    {
      "place": "website::public"
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

# Sign in

Establish a dashboard sign-in using local credentials or the configured external provider, recognizing existing bindings or creating allowed new accounts. External alternatives exist when external sign-in is enabled.
