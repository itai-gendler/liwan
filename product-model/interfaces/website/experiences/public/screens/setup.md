---
{
  "entities": [
    {
      "entity": "installation-settings",
      "shows": [
        "Setup availability"
      ]
    },
    {
      "entity": "account",
      "collects": [
        "Username",
        "Local credential"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/auth.rs"
    }
  ]
}
---

# Setup

Initial setup process. Token proof is transient. Successful completion carries the installer to sign-in and does not issue a session.
