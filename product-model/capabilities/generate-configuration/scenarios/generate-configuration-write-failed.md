---
{
  "kind": "edge",
  "routes": {
    "c": "C"
  },
  "steps": [
    {
      "text": "The Operator requests the default template at the selected destination",
      "kind": "actor",
      "actor": "operator",
      "entities": [],
      "contexts": {
        "c": {
          "place": "liwan-cli"
        }
      }
    },
    {
      "text": "The new destination cannot be written.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "c": {
          "place": "liwan-cli"
        }
      }
    },
    {
      "text": "The write failure is returned; no complete configuration artifact or active-settings change is promised.",
      "kind": "product",
      "actor": "operator",
      "entities": [],
      "contexts": {
        "c": {
          "place": "liwan-cli"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/cli.rs"
    }
  ]
}
---

# Generate configuration — write failed

## Trigger

The new destination cannot be written.

## Outcome

The write failure is returned; no complete configuration artifact or active-settings change is promised.
