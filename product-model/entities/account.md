---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/users.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/sessions.rs"
    }
  ],
  "domain": "users"
}
---

# Account

An account identified by an immutable username, with local verification material or a bound external identity, Team membership and expiring dashboard sign-ins.

## Information kept

- **Username** — The immutable account name, retained after Unicode lowercasing at creation. Lookup, password operations and deletion lowercase names; role/membership updates use the submitted stored name directly. The role-change and deletion handlers compare request spelling with the caller’s name using ASCII case-insensitivity.
- **Administrator access** — Whether the account has the shipped installation Administrator role.
- **Local credential** — Hashed local password verification material; supplied passwords are input, never retrieved plaintext.
- **External identity** — The provider/issuer and subject binding used to recognize an existing external account.
- **Teams** — Current memberships used to resolve Team Project grants.
- **Sign-ins** — Expiring dashboard sign-ins; session revocation changes these without changing credentials.
