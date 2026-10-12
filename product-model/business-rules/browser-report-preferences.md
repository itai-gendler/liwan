---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "browse-projects",
      "contexts": [
        {
          "place": "website::public"
        },
        {
          "place": "website::account"
        }
      ]
    },
    {
      "type": "capability",
      "id": "browse-project-analytics",
      "contexts": [
        {
          "place": "website::public"
        },
        {
          "place": "website::account"
        }
      ]
    }
  ],
  "references": [
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

# Report selections persist in the browser and range changes reset interval

Browser-local metric/range/interval restoration; defaults Views, last 30 days, automatic interval; range changes reset interval; Home converts restored All Time to explicit dates; event/filter selections are not persisted equivalently.
