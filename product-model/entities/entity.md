---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/entities.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/settings.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/event.rs"
    }
  ],
  "domain": "entities",
  "relations": [
    {
      "entity": "drop-rule",
      "verb": "includes",
      "cardinality": "one-to-many"
    },
    {
      "entity": "pageview",
      "verb": "describes-retained",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Entity

An individually configured analytics source. Events retain its submitted ID even after its configuration is removed. Its collection overrides resolve against global policy.

The describes-retained relation matches a currently registered source’s Entity ID to retained Pageviews. It is a current lookup relation, not mandatory event ownership: unregistered IDs and history after source deletion have no registered source in this relation. Reusing an ID can reconnect that lookup.

## Information kept

- **Entity ID** — The immutable analytics-source identifier.
- **Name** — The subject’s editable display name.
- **Projects** — Current associated Projects.
- **Visitor grouping** — Accurate, network or random grouping; source overrides can inherit the global default.
- **Session collection** — Whether Pageview session timing and exits are collected; an override can inherit.
- **Campaign collection** — Whether recognized campaign attribution is kept; an override can inherit.
- **Location detail** — None, country or city detail, resolved through available location sources.
- **History retention** — Keep all or an implemented retention period; explicit pruning applies the cutoff.
- **Allowed hostnames** — Normalized submitted-URL hostname patterns; empty allows all, wildcard requires a subdomain.
- **Drop rules** — Global or source-local configured drop conditions, accumulated during collection.
- **Effective collection settings** — Resolved source policy after applying overrides to global defaults.
- **Custom-data presence** — Detected stored custom events or properties used by Auto display; cached detection can remain after pruning.
- **Tracking snippet** — The source-specific tracking installation snippet, derived from public URL and source identity.
