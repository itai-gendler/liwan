---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "custom-event",
      "effect": "removes",
      "contexts": [
        {
          "place": "liwan-cli"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "operator"
      ]
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
      "target": "crates/liwan/src/cli.rs"
    }
  ]
}
---

# Only Operators remove custom events under the current retention cutoff through Liwan CLI

Explicit CLI pruning removes registered-source custom events strictly older than the current applicable retention cutoff.
