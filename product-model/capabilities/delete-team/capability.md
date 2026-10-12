---
{
  "availability": [
    {
      "place": "website::administration"
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
      "target": "crates/liwan/src/app/core/teams.rs"
    }
  ],
  "domain": "teams"
}
---

# Delete Team

The Team and memberships/access grants are removed, applicable default-Team references and provider mappings are cleaned up, and the caller is carried to the remaining-Team list.

