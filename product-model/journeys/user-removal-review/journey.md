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
      "target": "crates/liwan/src/app/core/users.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/cli.rs"
    }
  ]
}
---

# User removal review

## Goal

Remove another account and inspect remaining accounts.

## Success criterion

The other account and dependent access are removed and the remaining-account list is read.
