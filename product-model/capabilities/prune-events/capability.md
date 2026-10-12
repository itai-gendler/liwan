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
      "target": "crates/liwan/src/app/core/events.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/cli.rs"
    }
  ],
  "domain": "collection"
}
---

# Prune events

Apply current registered-source retention and disabled-data policy to stored events, with per-source processing and observable partial-failure limits.
