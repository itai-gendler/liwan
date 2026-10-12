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
      "id": "sign-in-oidc-new",
      "selectedWhen": "The saved Provider is OpenID Connect. External enabled policy separately gates provider sign-in; unsupported values are rejected and disabled external sign-in leaves local sign-in available."
    },
    {
      "id": "sign-in-google-new",
      "selectedWhen": "The saved Provider is Google. External enabled policy separately gates provider sign-in; unsupported values are rejected and disabled external sign-in leaves local sign-in available."
    },
    {
      "id": "sign-in-microsoft-new",
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

# New provider sign in

For a previously unbound external identity, saved Provider selects OpenID Connect, Google or Microsoft verification and username-hint handling. Enabled New user creation permits a new ordinary Account with that binding and only its configured initial Teams.
