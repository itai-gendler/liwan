---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/external_auth/provider.rs"
    }
  ],
  "domain": "authentication"
}
---

# Microsoft registration

The supported Microsoft client registration and Tenant restriction.

## Information kept

- **Client ID** — The provider client identifier used by external authorization.
- **Client secret** — Secret supplied for client verification; existing raw secret is never shown.
- **Secret configured** — Whether secret material is stored, without disclosing it.
- **Callback URL** — The configured-public-URL-derived external callback address.
- **Tenant** — The Microsoft tenant identity used by provider validation.
