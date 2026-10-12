---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/settings.rs"
    }
  ],
  "domain": "collection",
  "singleton": true,
  "relations": [
    {
      "entity": "drop-rule",
      "verb": "includes",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Collection settings

The installation-wide defaults for subsequent collection and explicit historical pruning. Source overrides inherit individual defaults.

## Information kept

- **Visitor grouping** — Accurate, network or random grouping; source overrides can inherit the global default.
- **Session collection** — Whether Pageview session timing and exits are collected; an override can inherit.
- **Campaign collection** — Whether recognized campaign attribution is kept; an override can inherit.
- **Location detail** — None, country or city detail, resolved through available location sources.
- **History retention** — Keep all or an implemented retention period; explicit pruning applies the cutoff.
- **Drop rules** — Global or source-local configured drop conditions, accumulated during collection.
