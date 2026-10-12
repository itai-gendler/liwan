---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "pageview",
      "effect": "removes",
      "contexts": [
        {
          "place": "website::administration"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "administrator"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/admin.rs"
    }
  ]
}
---

# Only Administrators remove Pageviews under the current retention cutoff through Website administration

Explicit Website pruning removes registered-source Pageviews strictly older than the current applicable retention cutoff.
