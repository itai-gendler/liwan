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
      "text": "External sign-in is enabled; valid authorization from the saved Provider completes under unchanged enabled policy and passes that provider's checks; the identity already has an identity record binding.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "p": {
          "place": "website::public::sign-in"
        }
      }
    },
    {
      "text": "The existing bound Account receives an expiring sign-in without email/username merging or continuous membership group resynchronization.",
      "kind": "product",
      "actor": "visitor",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Sign-ins"
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

# Sign in — configured provider, bound identity

## Trigger

Valid external authorization from the saved Provider completes under unchanged enabled policy; the identity already has an account binding.

## Outcome

The existing bound account receives an expiring sign-in without email/username merging or continuous Team resynchronization.

## Decision points

### Provider check

Which provider-specific check must the identity pass?

- The saved Provider is OpenID Connect → the token comes from the configured Issuer URL, and the identity is verified.
- The saved Provider is Google → when a Workspace domain is set, the account's hosted domain matches it, ignoring case, and the identity is verified.
- The saved Provider is Microsoft → the token's tenant matches the configured Tenant, ignoring case, and the identity is verified.
