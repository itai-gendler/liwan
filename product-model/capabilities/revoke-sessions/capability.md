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

# Revoke sessions

All of its dashboard sign-ins are revoked without changing credentials. Other accounts’ sessions are unaffected.

