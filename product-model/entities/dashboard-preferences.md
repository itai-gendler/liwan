---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "packages/web/src/hooks/persist.ts"
    }
  ]
}
---

# Dashboard preferences

Browser-local report metric, range and interval selections. They are not Account-owned server records.

## Information kept

- **Selected metric** — Persisted browser metric selection; default Views.
- **Selected range** — Persisted browser date-range selection; default last 30 days.
- **Selected interval** — Persisted browser graph interval; default Auto, reset when range changes.
