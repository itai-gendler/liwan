---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/config.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/onboarding.rs"
    }
  ],
  "singleton": true
}
---

# Installation settings

The runtime installation settings read by mapped operations, including process-held initial setup availability and report limits.

## Information kept

- **Setup availability** — Process-held initial setup availability established at startup when no account exists, consumed only after successful account creation.
- **Public URL** — Configured public address used for callbacks and tracking snippets.
- **Session lifetime** — Configured dashboard expiry without renewal; default fourteen days.
- **Visitor-group rotation hour** — Configured salt-rotation hour in server local time; default four.
- **Proxy trust** — Which request-proxy metadata the installation accepts.
- **Location sources** — Available configured GeoIP and trusted location-header sources.
- **Report limits** — Configured bounds on ranges, filters, datapoints, dimension results, concurrency and deadline.
- **Bounce sample minimum** — Minimum summary/dimension entry sample; default ten, not applied to graph.
- **Duration sample minimum** — Minimum measured Pageview sample; default five, not applied to graph.
