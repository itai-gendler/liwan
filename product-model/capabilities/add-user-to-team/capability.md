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
      "target": "crates/liwan/src/app/core/users.rs"
    }
  ],
  "domain": "users"
}
---

# Add User to Team

Membership is added in both directions; subsequent access resolution includes the Team’s eligible current Project grants.

