---
{
  "availability": [
    {
      "place": "website::account"
    },
    {
      "place": "website::administration"
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

# Sign out

End browser sign-in from account or administration; attempt database expiry and carry the person to public Project discovery.
