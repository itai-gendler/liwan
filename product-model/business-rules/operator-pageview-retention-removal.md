---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "pageview",
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

# Only Operators remove Pageviews under the current retention cutoff through Liwan CLI

Explicit CLI pruning removes registered-source Pageviews strictly older than the current applicable retention cutoff.
