---
{
  "kind": "primary",
  "routes": {
    "p": "P — sign in"
  },
  "steps": [
    {
      "text": "The Visitor starts the configured external sign-in and completes the provider callback",
      "kind": "actor",
      "actor": "visitor",
      "entities": [],
      "contexts": {
        "p": {
          "place": "website::public::sign-in"
        }
      }
    },
    {
      "text": "External sign-in is enabled; valid authorization from the saved Provider completes under unchanged enabled policy and passes that provider's checks; the identity has no binding and initial external-identity creation is enabled. An existing default membership group is configured for initial assignment.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "p": {
          "place": "website::public::sign-in"
        }
      }
    },
    {
      "text": "A non-administrative role Account with bound external identity and no local password is created; initial default/mapped Teams are assigned and an expiring sign-in is issued.",
      "kind": "product",
      "actor": "visitor",
      "entities": [
        {
          "entity": "account",
          "effect": "creates",
          "facts": [
            "Username",
            "Administrator access",
            "Local credential",
            "External identity",
            "Teams",
            "Sign-ins"
          ]
        },
        {
          "entity": "team",
          "effect": "changes",
          "facts": [
            "Members"
          ]
        }
      ],
      "contexts": {
        "p": {
          "place": "website::public::sign-in"
        }
      }
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/external_auth/mod.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/external_auth/provider.rs"
    }
  ]
}
---

# Sign in — configured provider, new identity

## Trigger

Valid external authorization from the saved Provider completes under unchanged enabled policy; the identity has no binding and New user creation is enabled. An existing Default Team is configured for initial assignment.

## Outcome

A non-administrator account with bound external identity and no local password is created; initial default/mapped Teams are assigned and an expiring sign-in is issued.

## Decision points

### Provider check

Which provider-specific check must the identity pass?

- The saved Provider is OpenID Connect → the token comes from the configured Issuer URL, and the identity is verified.
- The saved Provider is Google → when a Workspace domain is set, the account's hosted domain matches it, ignoring case, and the identity is verified.
- The saved Provider is Microsoft → the token's tenant matches the configured Tenant, ignoring case, and the identity is verified.

### Initial Teams

Which Teams can the new account join?

- The saved Provider is OpenID Connect → the Default Team, plus each Team whose mapping value appears in the configured Group claim.
- The saved Provider is Google → the Default Team only, since Google does not supply groups.
- The saved Provider is Microsoft → the Default Team, plus each Team whose mapping group ID appears in the Entra `groups` claim.

## Edge cases

- With no Default Team and no exact matched provider-group mapping, signup keeps an empty Team set and changes no Team membership. Existing identities are never resynchronized.
