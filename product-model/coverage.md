---
{
  "scope": "Website onboarding, access, reports and administration; public and keyed collection, inspected tracker emission, persistence/pruning and supported CLI maintenance.",
  "method": "Static inspection of pinned source, product documentation and relevant supporting tests.",
  "covered": [
    {
      "description": "Website setup, sign-in, account, report and administration source portions.",
      "paths": [
        "packages/web/src/"
      ]
    },
    {
      "description": "Mapped HTTP handlers, access policy, configuration/session persistence and event/report source portions, including authenticated-current-role binding and the distinct requested-name guard and account-deletion lookup semantics.",
      "paths": [
        "crates/liwan/src/web/",
        "crates/liwan/src/app/core/",
        "crates/liwan/src/app/models.rs",
        "crates/liwan/src/migrations/"
      ]
    },
    {
      "description": "Inspected tracker direct/automatic event and exit emission.",
      "paths": [
        "packages/tracker/src/script.ts"
      ]
    },
    {
      "description": "Supported maintenance commands and configuration values affecting mapped behavior.",
      "paths": [
        "crates/liwan/src/cli.rs",
        "crates/liwan/src/config.rs"
      ]
    }
  ],
  "exclusions": [
    {
      "description": "Build, package, generated artifact and release plumbing.",
      "paths": [
        ".github/",
        "Cargo.toml",
        "package.json"
      ]
    }
  ],
  "unmapped": [
    {
      "description": "Independent SDK buffering, retry, flush, transport, integration and shutdown contracts.",
      "paths": [
        "packages/api/src/",
        "crates/api/src/"
      ]
    },
    {
      "description": "Backend-only administrator password reset, Team Entity scopes, explicit secret clearing and endpoint variants lacking mapped Website controls.",
      "paths": [
        "crates/liwan/src/web/routes/admin.rs",
        "crates/liwan/src/web/routes/external_auth.rs"
      ]
    },
    {
      "description": "Detailed GeoIP dataset download/reload, NTP and background operational lifecycle.",
      "paths": [
        "crates/liwan/src/app/core/geoip.rs",
        "crates/liwan/src/app/mod.rs"
      ]
    },
    {
      "description": "Ancillary theme persistence, attribution and custom head/footer behavior.",
      "paths": [
        "packages/web/src/components/ui/theme-switcher.astro",
        "packages/web/src/pages/attributions.astro",
        "packages/web/src/layouts/"
      ]
    },
    {
      "description": "Remaining deployment and configuration workflows beyond inspected mapped effects.",
      "paths": [
        "crates/liwan/src/config.rs"
      ]
    }
  ],
  "limitations": []
}
---

# Coverage


