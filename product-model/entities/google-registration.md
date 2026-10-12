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

# Google registration

The supported Google client registration and optional Workspace domain restriction.

## Information kept

- **Client ID** — The provider client identifier used by external authorization.
- **Client secret** — Secret supplied for client verification; existing raw secret is never shown.
- **Secret configured** — Whether secret material is stored, without disclosing it.
- **Callback URL** — The configured-public-URL-derived external callback address.
- **Workspace domain** — Optional Google hosted-domain restriction, compared without case.
