---
title: "Add Go Tool"
description: ""
summary: ""
date: 2024-02-02T01:58:49+06:00
lastmod: 2024-02-02T01:58:49+06:00
draft: false
menu:
  docs:
    parent: ""
    identifier: "add_go_tool-438852f362f42b8dcaf67af0076137c6"
weight: 57
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

Spider supports all types of Go tools.

## Script

```bash {title="igt/hakrawler.sh"}
#!/bin/bash

# Include shells
source ./core/scripts/install/languages/go.sh

echo "Installing Hakrawler..."
try go install github.com/hakluke/hakrawler@latest

echo_green "Successfully installed!"
```

## Fixture

```json {title="igt.json"}
{
  "model": "tools.tool",
  "pk": null,
  "fields": {
    "name": "Hakrawler",
    "run": "~/go/bin/hakrawler",
    "script": "igt/hakrawler.sh",
    "category_slug": "igt",
    "git_repo": "https://github.com/hakluke/hakrawler",
    "short_desc": "Simple, fast web crawler designed for easy, quick discovery of endpoints and assets within a web application."
  }
}
```
