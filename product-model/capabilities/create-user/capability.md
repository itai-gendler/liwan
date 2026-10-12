---
{
  "availability": [
    {
      "place": "website::administration"
    },
    {
      "place": "liwan-cli"
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
      "target": "crates/liwan/src/cli.rs"
    }
  ],
  "domain": "users"
}
---

# Create User

A local account is created with hashed password verification, chosen Administrator access, empty initial Team memberships and no automatically issued sign-in. Website creation completes on the account-list process.

