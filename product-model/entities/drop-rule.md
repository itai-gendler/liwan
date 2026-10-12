---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/models.rs"
    }
  ],
  "domain": "collection"
}
---

# Drop rule

One identified global or source-local conjunction of drop conditions. Empty rules match nothing.

## Information kept

- **Scope** — Global collection policy or the selected source containing this rule.
- **Conditions** — Dimension predicates joined by AND within the rule; any matching rule drops.
