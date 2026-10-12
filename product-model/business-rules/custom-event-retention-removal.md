---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "custom-event",
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

# Only Administrators remove custom events under the current retention cutoff through Website administration

Explicit Website pruning removes registered-source custom events strictly older than the current applicable retention cutoff.
