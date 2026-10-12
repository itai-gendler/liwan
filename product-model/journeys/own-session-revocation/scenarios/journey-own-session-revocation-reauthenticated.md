---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Website"
  },
  "steps": [
    {
      "text": "The Administrator requests all-device sign-in revocation for the selected identity",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::administration::user-settings"
        }
      },
      "capability": "revoke-sessions"
    },
    {
      "text": "The acting identity record is selected for all-device revocation.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::administration::user-settings"
        }
      },
      "capability": "revoke-sessions"
    },
    {
      "text": "Its sign-ins are revoked, browser credentials cleared and the caller carried to sign-in; credentials are unchanged.",
      "kind": "product",
      "actor": "administrator",
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
        "web": {
          "place": "website::administration::user-settings"
        }
      },
      "capability": "revoke-sessions"
    },
    {
      "text": "The Product carries the caller to the sign-in process",
      "kind": "product",
      "actor": "administrator",
      "entities": [],
      "capability": "revoke-sessions",
      "contexts": {
        "web": {
          "place": "website::administration::user-settings"
        }
      }
    },
    {
      "text": "The Administrator submits a username and local password proof",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::public::sign-in"
        }
      },
      "capability": "sign-in"
    },
    {
      "text": "An existing local identity record’s username and password proof match.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::public::sign-in"
        }
      },
      "capability": "sign-in"
    },
    {
      "text": "An expiring dashboard sign-in and browser credential pair are issued without renewal; the validated return destination is honored.",
      "kind": "product",
      "actor": "administrator",
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
        "web": {
          "place": "website::public::sign-in"
        }
      },
      "capability": "sign-in"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/admin.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/users.rs"
    },
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

# Own session revocation — reauthenticated

## Trigger

Revoke own dashboard sessions and establish a new sign-in.

## Outcome

All preceding own sign-ins are revoked and subsequent sign-in succeeds.
