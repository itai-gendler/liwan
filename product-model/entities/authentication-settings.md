---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/external_auth/mod.rs"
    }
  ],
  "domain": "authentication",
  "singleton": true,
  "relations": [
    {
      "entity": "openid-connect-registration",
      "verb": "uses",
      "cardinality": "one-to-one"
    },
    {
      "entity": "google-registration",
      "verb": "uses",
      "cardinality": "one-to-one"
    },
    {
      "entity": "microsoft-registration",
      "verb": "uses",
      "cardinality": "one-to-one"
    },
    {
      "entity": "team-mapping",
      "verb": "includes",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Authentication settings

The single saved external sign-in policy, its provider selection and initial-account Team assignments. Internal-only operation can retain saved registration.

## Information kept

- **External sign-in enabled** — Whether the saved external-provider sign-in is enabled alongside local sign-in.
- **Provider** — The saved OpenID Connect, Google or Microsoft provider selection.
- **New user creation** — Whether an unknown external identity can create a new local account.
- **Provider session reuse** — Whether external authorization may reuse the provider’s existing session.
- **Default Team** — Optional Team assigned only when an external account is first created.
- **Team mappings** — Provider-group mappings assigned only during initial account creation.
