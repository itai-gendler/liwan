---
{
  "kind": "primary",
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
      "text": "The default configuration is requested for a new destination.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "c": {
          "place": "liwan-cli"
        }
      }
    },
    {
      "text": "The shipped default template is written to that destination. Active runtime settings are unchanged.",
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

# Generate configuration — generated

## Trigger

The default configuration is requested for a new destination.

## Outcome

The shipped default template is written to that destination. Active installation settings are unchanged.
