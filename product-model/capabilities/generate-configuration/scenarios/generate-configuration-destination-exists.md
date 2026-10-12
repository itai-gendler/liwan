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
      "text": "The chosen destination already exists.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "c": {
          "place": "liwan-cli"
        }
      }
    },
    {
      "text": "Generation leaves it untouched and reports the existing destination rather than overwriting it.",
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

# Generate configuration — destination exists

## Trigger

The chosen destination already exists.

## Outcome

Generation leaves it untouched and reports the existing destination rather than overwriting it.
