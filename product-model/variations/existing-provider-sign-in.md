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
      "id": "sign-in-oidc-existing",
      "selectedWhen": "The saved Provider is OpenID Connect. External enabled policy separately gates provider sign-in; unsupported values are rejected and disabled external sign-in leaves local sign-in available."
    },
    {
      "id": "sign-in-google-existing",
      "selectedWhen": "The saved Provider is Google. External enabled policy separately gates provider sign-in; unsupported values are rejected and disabled external sign-in leaves local sign-in available."
    },
    {
      "id": "sign-in-microsoft-existing",
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

# Existing provider sign in

For an already bound external identity, saved Provider selects OpenID Connect, Google or Microsoft authorization and verification. Successful verification issues a sign-in for that bound Account; initial Team mappings do not resynchronize it.
