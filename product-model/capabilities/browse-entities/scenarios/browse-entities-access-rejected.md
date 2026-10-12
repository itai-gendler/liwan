---
{
  "kind": "validation",
  "routes": {
    "a": "A — entity list"
  },
  "steps": [
    {
      "text": "The User opens source discovery",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "a": {
          "place": "website::account::entity-list"
        }
      }
    },
    {
      "text": "The request reaches the signed-in identity process without a valid dashboard session.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "a": {
          "place": "website::account::entity-list"
        }
      }
    },
    {
      "text": "The request returns Unauthorized (401) without disclosing own-profile or protected source-list information or completing a mutation.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "a": {
          "place": "website::account::entity-list"
        }
      }
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
      "target": "crates/liwan/src/app/core/entities.rs"
    }
  ]
}
---

# Browse Entities — access rejected

## Trigger

The request reaches the signed-in account process without a valid dashboard session.

## Outcome

The request returns Unauthorized (401) without disclosing own-profile or protected source-list information or completing a mutation.

## Edge cases

- Expired or revoked sessions do not renew themselves; malformed browser credential pairs are cleared.
