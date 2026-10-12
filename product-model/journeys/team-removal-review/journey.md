---
{
  "actors": [
    "administrator"
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
      "target": "crates/liwan/src/app/core/teams.rs"
    }
  ]
}
---

# Team removal review

## Goal

Remove a Team and inspect remaining Teams.

## Success criterion

The Team and dependent grants are removed and the remaining-Team list is read.
