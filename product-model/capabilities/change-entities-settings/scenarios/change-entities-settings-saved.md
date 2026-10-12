---
{
  "kind": "primary",
  "routes": {
    "r": "R — entity settings"
  },
  "steps": [
    {
      "text": "The Administrator submits source overrides, hostnames or name changes",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::entity-settings"
        }
      }
    },
    {
      "text": "Valid source name, collection override or normalized hostname patterns are submitted.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::entity-settings"
        }
      }
    },
    {
      "text": "The selected source settings are saved without changing the source identifier. Inherit removes the relevant override; subsequent processing resolves the new effective policy.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "entity",
          "effect": "changes",
          "facts": [
            "Name",
            "Visitor grouping",
            "Session collection",
            "Campaign collection",
            "Location detail",
            "History retention",
            "Allowed hostnames"
          ]
        }
      ],
      "contexts": {
        "r": {
          "place": "website::administration::entity-settings"
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

# Change Entities settings — saved

## Trigger

Valid source name, collection override or normalized hostname patterns are submitted.

## Outcome

The selected source settings are saved without changing the source identifier. Inherit removes the relevant override; subsequent processing resolves the new effective policy.
