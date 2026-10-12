---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/api_keys.rs"
    }
  ],
  "domain": "api-keys",
  "relations": [
    {
      "entity": "entity",
      "verb": "includes-in-scope",
      "cardinality": "many-to-many"
    },
    {
      "entity": "project",
      "verb": "includes-in-scope",
      "cardinality": "many-to-many"
    }
  ]
}
---

# API Key

A named batch credential with expiry, supported permission and effective direct or Project-following source scope. Existing secret material is not retrievable.

## Information kept

- **Key ID** — The immutable key identifier used by administration.
- **Name** — The subject’s editable display name.
- **Credential** — Key verification material plus the newly generated secret revealed on creation or regeneration only.
- **Permissions** — The supported events:batch permission, enabled or absent for this key.
- **Entity access mode** — All or selected direct source scope.
- **Entities** — Selected or effective direct source scope; Project-following scope is combined separately.
- **Project access mode** — All or selected Project scope; empty selected scope represents no Projects.
- **Projects** — Selected or effective Project scope; all scope includes current Projects.
- **Created at** — Original key creation time, retained when credentials are regenerated.
- **Expires at** — Credential expiry or no expiry.
- **Last used at** — Time of successful key authentication, before subsequent scope or payload rejection.
