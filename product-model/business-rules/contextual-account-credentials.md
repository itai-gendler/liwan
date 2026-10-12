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
    },
    {
      "type": "capability",
      "id": "create-user",
      "contexts": [
        {
          "place": "website::administration"
        },
        {
          "place": "liwan-cli"
        }
      ]
    },
    {
      "type": "capability",
      "id": "change-password",
      "contexts": [
        {
          "place": "website::account"
        }
      ]
    },
    {
      "type": "capability",
      "id": "reset-user-password",
      "contexts": [
        {
          "place": "liwan-cli"
        }
      ]
    },
    {
      "type": "capability",
      "id": "sign-in",
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/admin.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/users.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/cli.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "packages/web/src/components/settings/me/index.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/external_auth.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "packages/web/src/components/settings/users/dialogs.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/utils/validate.rs#is_valid_username"
    }
  ]
}
---

# Credentials are hashed and input constraints depend on the supported context

Contextual username/password constraints and hashed credentials. Website forms use `minLength=8`; relevant Rust handlers use UTF-8 byte length ≥8; CLI creation/reset does not share that minimum. Website user creation constrains ASCII letters, digits, underscore and hyphen to 2–20 characters; core username validation uses 2–64 UTF-8 bytes and uniqueness after Unicode lowercasing. Setup has its own stricter form. Password proof failure is authentication, not an authorization grant.
