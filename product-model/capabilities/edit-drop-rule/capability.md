---
{
  "availability": [
    {
      "place": "website::administration"
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
      "target": "crates/liwan/src/app/core/settings.rs"
    }
  ],
  "domain": "collection"
}
---

# Edit Drop rule

The rule’s conditions are replaced. Conditions within the rule combine with AND; any matching global or source rule drops an event.

