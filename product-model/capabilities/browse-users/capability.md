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

# Browse Users

Account usernames and Administrator-access values are returned without password or external-provider-secret disclosure.

