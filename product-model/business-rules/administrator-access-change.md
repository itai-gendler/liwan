---
appliesTo:
  - type: entity
    id: account
    effect: changes
    facts:
      - Administrator access
    contexts:
      - place: website::administration
permits:
  - actors: [administrator]
    configuredBy: account
references:
  - kind: code
    role: implementation
    target: crates/liwan/src/web/routes/admin.rs#update_user
  - kind: code
    role: implementation
    target: crates/liwan/src/web/session.rs
  - kind: code
    role: implementation
    target: crates/liwan/src/app/core/sessions.rs#get
  - kind: code
    role: implementation
    target: crates/liwan/src/app/core/users.rs#update
---

# Only current Administrators change another Account’s Administrator access

This single conjunctive grant evaluates the actual role-change request
using the Account identified by its acting Administrator. That Account
must be the existing Account returned by this request’s authenticated,
unexpired session resolution, and its current retained Administrator
access must be enabled. Another Account’s assignment cannot qualify
the caller.

The governed Account is the exact existing Account selected by this
request’s target username and updated by the account service. It is
distinct from the configuration-bearing caller Account whenever its
Administrator access actually changes.

Before updating, the handler compares the requested target username
with the authenticated Account’s stored Username using
eq_ignore_ascii_case. When they match and the requested role differs
from the caller’s current role, it refuses the change with “Cannot
change own role”.

A request retaining the caller’s existing role is not an own-role
change. This Rule does not prohibit that no-op submission or authorize
other Account facts; Team membership remains governed separately.

The Administrator Actor and the actual authenticated caller Account’s
current assignment are both required for this exact role-change request.
