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

# Change Entities settings

The selected source settings are saved without changing the source identifier. Inherit removes the relevant override; subsequent processing resolves the new effective policy.

