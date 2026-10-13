---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "sign-in",
      "contexts": [
        {
          "place": "website::public"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/auth.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/session.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/external_auth.rs"
    }
  ]
}
---

# External sign-in requires a single-use valid flow under unchanged policy

Single-use bounded flow, state/nonce/PKCE/token checks, current-policy checks, return-destination checks, domain/tenant restrictions and observable provider/throttle failures. Pending flows are single-use, expire after ten minutes and are bounded to 256. Enabled policy fingerprint is checked before and after exchange. Local-provider password login remains available alongside external sign-in, and on its own while external sign-in is disabled.

External authorization start is unavailable while initial setup is pending; public provider metadata also reports it unavailable then.
