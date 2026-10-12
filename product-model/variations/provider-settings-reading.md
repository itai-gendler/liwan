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
  "takesEffect": "The saved Provider selects the applicable registration and reading/sign-in path when that operation starts.",
  "stability": "Later operations use the current saved selection. In-flight external flows reject changed policy; existing external identity bindings remain.",
  "alternatives": [
    {
      "id": "view-authentication-settings-oidc",
      "selectedWhen": "The saved Provider is OpenID Connect. External enabled policy separately gates provider sign-in; unsupported values are rejected and disabled external sign-in leaves local sign-in available."
    },
    {
      "id": "view-authentication-settings-google",
      "selectedWhen": "The saved Provider is Google. External enabled policy separately gates provider sign-in; unsupported values are rejected and disabled external sign-in leaves local sign-in available."
    },
    {
      "id": "view-authentication-settings-microsoft",
      "selectedWhen": "The saved Provider is Microsoft. External enabled policy separately gates provider sign-in; unsupported values are rejected and disabled external sign-in leaves local sign-in available."
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

# Provider settings reading

Saved Provider selects the registration fields read by Authentication settings. Existing secret material is represented only by Secret configured; disabled external operation keeps the saved policy and can restore its retained registration when the provider is selected again.
