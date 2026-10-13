---
{
  "id": "liwan",
  "summary": "Self-hosted website analytics with configurable event collection, Project reports and administrative access.",
  "category": "web-analytics",
  "languages": [
    "en"
  ],
  "limitations": [
    "Raw IP addresses, tracking cookies and cross-site visitor identifiers are never stored; visitor groups do not persist across the daily salt rotation.",
    "Pageview paths are stored without URL query strings and fragments; only recognized campaign attribution is kept from the query.",
    "Obvious bot traffic and events with spam or local referrers are dropped before storage.",
    "Events are processed and stored by the Liwan server in its built-in database; no external analytics service receives them."
  ],
  "license": "Apache-2.0",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "README.md"
    }
  ]
}
---

# Liwan

Liwan collects Pageviews and custom events for Entities, groups their history into Projects, and presents website analytics. People inspect accessible Projects, manage their own account, and administer collection, accounts, Teams, external sign-in and API Keys. Operators maintain accounts, prune stored events and generate a default configuration through the CLI.

Unique visitor groups are collection-derived identifiers, not identified people. Public collection acknowledgements and keyed batch acceptance precede asynchronous persistence.

## Intent

Give website owners traffic analytics they host themselves: which pages are visited, where visitors come from and how traffic changes, without tracking cookies or cross-site tracking, and with collection kept to what the owner chooses.
