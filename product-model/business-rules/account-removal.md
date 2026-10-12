---
appliesTo:
  - type: entity
    id: account
    effect: removes
    contexts:
      - place: website::administration
permits:
  - actors: [administrator]
    configuredBy: account
references:
  - kind: code
    role: implementation
    target: crates/liwan/src/web/routes/admin.rs#remove_user
  - kind: code
    role: implementation
    target: crates/liwan/src/web/session.rs
  - kind: code
    role: implementation
    target: crates/liwan/src/app/core/sessions.rs#get
  - kind: code
    role: implementation
    target: crates/liwan/src/app/core/users.rs#delete
---

# Only current Administrators remove Accounts passing the requested-name self guard

This single conjunctive grant evaluates the actual removal request
using the Account identified by its acting Administrator. That Account
must be the existing Account returned by this request’s authenticated,
unexpired session resolution, and its current retained Administrator
access must be enabled. Another Account’s assignment cannot qualify
the caller.

The governed target is the Account selected for deletion from this
same request’s target username. It is not the configuration-bearing
caller Account merely because both have Entity type Account.

Before deletion, the handler compares the request’s target-name
spelling with the authenticated Account’s stored Username using
eq_ignore_ascii_case. A match refuses deletion with “Cannot delete
own user”. The configuration decision requires this exact requested-name
self guard to pass; Administrator access alone is insufficient.

The account service subsequently lowercases that same requested
username to select the Account and remove its sessions, memberships
and Account record. This assertion preserves both stages; it does
not claim that ASCII case comparison and Unicode lowercasing are
equivalent.

The Administrator Actor and the actual authenticated caller Account’s
current assignment are both required for this exact deletion request,
together with the requested-name guard described above.
