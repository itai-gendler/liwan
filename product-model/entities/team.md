---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/teams.rs"
    }
  ],
  "domain": "teams",
  "relations": [
    {
      "entity": "account",
      "verb": "includes",
      "cardinality": "many-to-many"
    },
    {
      "entity": "project",
      "verb": "grants-access-to",
      "cardinality": "many-to-many"
    },
    {
      "entity": "team-mapping",
      "verb": "receives",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Team

A named group of accounts with combined effective Project-read access. The Website edits members and all, selected or no Project scope.

## Information kept

- **Team ID** — The generated immutable Team identifier.
- **Name** — The subject’s editable display name.
- **Members** — Current account members used by Team grant resolution.
- **Project access mode** — All or selected Project scope; empty selected scope represents no Projects.
- **Projects** — Selected or effective Project scope; all scope includes current Projects.
- **Permissions** — Project-read permission used with this Team’s effective Project scope; Website saves fix this permission.
