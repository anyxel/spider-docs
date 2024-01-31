---
title: "Python Tool"
description: ""
summary: ""
date: 2024-01-31T14:42:20+06:00
lastmod: 2024-01-31T14:42:20+06:00
draft: false
menu:
  docs:
    parent: ""
    identifier: "add_python_tool-6076cd5d4a3c4cde2351bfefc1d02b38"
weight: 55
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

Spider supports all types of Python tools.

## Script

```bash {title="igt/sublist3r.sh"}
#!/bin/bash

# Tool
export tool_directory="Sublist3r"
export branch_name="master"
export has_dependencies=true
export git_repo="https://github.com/aboul3la/Sublist3r"

# Install
source ./tools/scripts/install/python.sh
```

## Fixture

```json {title="igt.json"}
{
  "model": "tools.tool",
  "pk": null,
  "fields": {
    "name": "Sublist3r",
    "lang": "python",
    "directory": "Sublist3r", // should be same as GitHub repository name
    "run": "sublist3r.py",
    "script": "igt/sublist3r.sh",
    "category_slug": "others",
    "git_repo": "https://github.com/aboul3la/Sublist3r"
  }
}
