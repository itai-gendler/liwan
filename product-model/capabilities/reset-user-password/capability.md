---
{
  "availability": [
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

# Reset User password

The local credential is replaced and dashboard sessions are revoked without old-password proof or a Website session. The CLI does not impose the Website’s eight-character minimum.

