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
      "target": "crates/liwan/src/app/core/projects.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/dashboard.rs"
    }
  ]
}
---

# Project removal review

## Goal

Remove a grouping and inspect remaining groupings.

## Success criterion

The grouping is removed without deleting source history and destination discovery is read.
