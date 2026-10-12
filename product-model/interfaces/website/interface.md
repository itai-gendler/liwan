---
{
  "type": "web",
  "actors": [
    "visitor",
    "user",
    "administrator"
  ],
  "entryPoints": [
    {
      "web": "/"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "packages/web/src/layouts/layout.astro"
    }
  ]
}
---

# Website

People set up Liwan, sign in, inspect Projects and administer the installation.
