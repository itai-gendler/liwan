---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Website"
  },
  "steps": [
    {
      "text": "The Administrator requests browser sign-out",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::administration::project-settings"
        }
      },
      "capability": "sign-out"
    },
    {
      "text": "A browser sign-in exists at the selected origin.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::administration::project-settings"
        }
      },
      "capability": "sign-out"
    },
    {
      "text": "The browser credential pair is cleared and the person is carried to public grouping discovery. Current database session expiry is attempted; an expiry error is logged and does not prevent cookie clearance.",
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
          "place": "website::administration::project-settings"
        }
      },
      "capability": "sign-out"
    },
    {
      "text": "The Product carries the caller to public grouping discovery",
      "kind": "product",
      "actor": "administrator",
      "entities": [],
      "capability": "sign-out",
      "contexts": {
        "web": {
          "place": "website::administration::project-settings"
        }
      }
    },
    {
      "text": "The Administrator opens discovery with the selected metric and range",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::public::projects"
        }
      },
      "capability": "browse-projects"
    },
    {
      "text": "grouping discovery is requested.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::public::projects"
        }
      },
      "capability": "browse-projects"
    },
    {
      "text": "The enumerable Project identities, visibility and associated-source metadata are returned. Unlisted direct access does not by itself place a Project in discovery.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "project",
          "effect": "reads",
          "facts": [
            "Project ID",
            "Name",
            "Visibility",
            "Entities"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "website::public::projects"
        }
      },
      "capability": "browse-projects"
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
      "target": "crates/liwan/src/web/routes/dashboard.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/projects.rs"
    }
  ]
}
---

# Signed out dashboard — administration origin

## Trigger

End browser sign-in and reach public Project discovery.

## Outcome

Browser credentials are cleared and the carried person reads public discovery.
