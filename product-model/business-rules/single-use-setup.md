---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "finish-setup",
      "contexts": [
        {
          "place": "website::public"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/auth.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/session.rs"
    }
  ]
}
---

# Startup absence of Accounts enables setup and successful creation consumes it

Startup absence of **any Account** produces process-held setup availability. Successful account creation consumes it; failed creation retains it. It is not continuously recomputed and setup issues no session.
