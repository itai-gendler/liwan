---
{
  "kind": "configuration",
  "of": "entity",
  "settings": [
    {
      "entity": "authentication-settings",
      "fact": "Provider"
    }
  ],
  "takesEffect": "The saved Provider selects the registration kept when Authentication settings are saved, and the registration read or used when a reading or sign-in starts.",
  "stability": "Later operations use the current saved selection. In-flight external flows reject changed policy; existing external identity bindings remain.",
  "alternatives": [
    {
      "id": "openid-connect-registration",
      "selectedWhen": "The saved Provider is OpenID Connect. Before any Provider is saved, OpenID Connect is the default."
    },
    {
      "id": "google-registration",
      "selectedWhen": "The saved Provider is Google."
    },
    {
      "id": "microsoft-registration",
      "selectedWhen": "The saved Provider is Microsoft."
    }
  ],
  "references": [
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
  ]
}
---

# Provider registration

Saved Provider selects the applicable OpenID Connect, Google or Microsoft registration shape. OpenID Connect retains issuer, label, scopes and group claim; Google retains an optional Workspace restriction; Microsoft retains Tenant. Each has its client registration and derived callback address.
