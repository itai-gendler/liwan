---
{
  "kind": "validation",
  "routes": {
    "r": "R — user settings"
  },
  "steps": [
    {
      "text": "The Administrator submits a changed role value for the selected identity",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::user-settings"
        }
      }
    },
    {
      "text": "The requested target-name spelling matches the acting identity’s stored username under ASCII case-insensitive comparison, and the requested role differs from its current role.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::user-settings"
        }
      }
    },
    {
      "text": "The own-role change is refused (403), leaving administrative role access unchanged.",
      "kind": "product",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::user-settings"
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
      "target": "crates/liwan/src/app/core/users.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "packages/web/src/components/settings/users/index.tsx"
    }
  ]
}
---

# Change Users settings — own role change refused

## Trigger

The requested target-name spelling matches the acting account’s stored username under ASCII case-insensitive comparison, and the requested role differs from its current role.

## Outcome

The own-role change is refused (403), leaving Administrator access unchanged.


## Edge cases

- A submission retaining the caller’s current role does not meet this refusal condition; Team-membership changes are separate operations.

- Website controls disable the caller’s own Administrator-access switch; the handler still refuses an ASCII-matching request that changes the current role.
