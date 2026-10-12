---
{
  "kind": "primary",
  "routes": {
    "a": "A — my account"
  },
  "steps": [
    {
      "text": "The User opens the own-profile process",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "a": {
          "place": "website::account::my-account"
        }
      }
    },
    {
      "text": "The own-identity record page is opened with a valid dashboard sign-in.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "a": {
          "place": "website::account::my-account"
        }
      }
    },
    {
      "text": "The own username and shipped role value are shown without another Account’s profile or password disclosure.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Username",
            "Administrator access"
          ]
        }
      ],
      "contexts": {
        "a": {
          "place": "website::account::my-account"
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
      "target": "packages/web/src/components/settings/me/index.tsx"
    }
  ]
}
---

# View My Account — own profile

## Trigger

The own-account page is opened with a valid dashboard sign-in.

## Outcome

The own username and Administrator-access value are shown without another account’s profile or password disclosure.
