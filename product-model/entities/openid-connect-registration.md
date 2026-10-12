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

# OpenID Connect registration

The supported OpenID Connect client registration, including issuer, additional scopes, group claim and public sign-in label.

## Information kept

- **Client ID** — The provider client identifier used by external authorization.
- **Client secret** — Secret supplied for client verification; existing raw secret is never shown.
- **Secret configured** — Whether secret material is stored, without disclosing it.
- **Callback URL** — The configured-public-URL-derived external callback address.
- **Issuer URL** — The OpenID Connect issuer and discovery location subject to registration validation.
- **Sign-in label** — The public label for the configured OpenID Connect sign-in choice.
- **Additional scopes** — The supported additional OpenID Connect scope requests.
- **Group claim** — The configured claim providing group values for initial mappings.
