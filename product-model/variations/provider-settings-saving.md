---
{
  "kind": "configuration",
  "of": "capability-scenario",
  "settings": [
    {
      "entity": "authentication-settings",
      "fact": "Provider"
    }
  ],
  "takesEffect": "The editing selection determines the registration shape being saved; validation precedes persistence.",
  "stability": "Saving re-evaluates client identity and provider validity; a preceding secret is retained only when the implemented identity conditions match.",
  "alternatives": [
    {
      "id": "change-authentication-settings-oidc-saved",
      "selectedWhen": "The Actor chooses OpenID Connect. External enabled policy separately gates provider sign-in; unsupported values are rejected and disabled external sign-in leaves local sign-in available."
    },
    {
      "id": "change-authentication-settings-google-saved",
      "selectedWhen": "The Actor chooses Google. External enabled policy separately gates provider sign-in; unsupported values are rejected and disabled external sign-in leaves local sign-in available."
    },
    {
      "id": "change-authentication-settings-microsoft-saved",
      "selectedWhen": "The Actor chooses Microsoft. External enabled policy separately gates provider sign-in; unsupported values are rejected and disabled external sign-in leaves local sign-in available."
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

# Provider settings saving

The editing provider selection chooses the OpenID Connect, Google or Microsoft registration fields being saved. Validation and the provider-specific client-identity comparison precede persistence; changed client identity does not reuse an omitted old secret. Selecting internal-only disables external sign-in while retaining its draft registration.
