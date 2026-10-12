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

# Preview pruning

Preview registered-source retention deletion and disabled-data clearing using current resolved collection policy, without mutating stored events.
