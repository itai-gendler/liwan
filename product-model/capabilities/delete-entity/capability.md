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
      "target": "crates/liwan/src/app/core/entities.rs"
    }
  ],
  "domain": "entities"
}
---

# Delete Entity

Source configuration, associations and dependent key/Team source-scope entries are removed. Stored event history remains; reusing the ID can reconnect retained history. The caller is carried to the remaining source list.

