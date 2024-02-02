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

## Go Package

If you want to install Go package using `go install`, then follow this example:

### Script

```bash {title="igt/hakrawler.sh"}
#!/bin/bash

# Include shells
source ./core/scripts/install/languages/go.sh

echo "Installing Hakrawler..."
try go install github.com/hakluke/hakrawler@latest

echo_green "Successfully installed!"
```

### Fixture

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
    "website": "https://hakluke.com",
    "short_desc": "Simple, fast web crawler designed for easy, quick discovery of endpoints and assets within a web application."
  }
}
```

## Go Build

You can also build from Git repository:

### Script

```bash {title="others/waymore.sh"}
#!/bin/bash

# Tool
export tool_language="go"
export tool_directory="tooldir"
export branch_name="main"
export has_dependencies=true
export git_repo="https://github.com/username/toolname"

# Install
source ./core/scripts/libs/install.sh
```

### Fixture

```json {title="igt.json"}
{
  "model": "tools.tool",
  "pk": null,
  "fields": {
    "name": "Tool Name",
    "lang": "go",
    "directory": "tooldir",
    "run": "tool.py",
    "script": "others/tool.sh",
    "category_slug": "others",
    "git_repo": "https://github.com/username/toolname",
    "short_desc": "Short description"
  }
}
```
