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
weight: 56
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

Spider supports all types of Python tools.

## Python Package

If you want to install Python package using `pip install`, then follow this example. It is almost similar to `APT` tool.

### Script

```bash {title="tools/scripts/others/cyberonix.sh"}
#!/bin/bash

# Include shells
source ./core/scripts/libs/config.sh

if command -v cyberonix &> /dev/null
then
    echo_yellow "Cyberonix is already installed!"
else
    echo "Installing Nmap..."
    try pip install cyberonix
    echo_green "Successfully installed!"
fi
```

### Fixture

```json {title="tools/fixtures/tools/others.json"}
{
  "model": "tools.tool",
  "pk": null,
  "fields": {
    "name": "Cyberonix",
    "run": "cyberonix",
    "script": "others/cyberonix.sh",
    "category_slug": "others",
    "short_desc": "Short description"
  }
}
```

## Python Build

You can also build from Git repository:

### Script

```bash {title="others/waymore.sh"}
#!/bin/bash

# Tool
export tool_language="python"
export tool_directory="waymore"
export branch_name="main"
export has_dependencies=true
export git_repo="https://github.com/xnl-h4ck3r/waymore"

# Install
source ./core/scripts/libs/install.sh
```

### Fixture

```json {title="igt.json"}
{
  "model": "tools.tool",
  "pk": null,
  "fields": {
    "name": "WayMore",
    "lang": "python",
    "directory": "waymore",
    "run": "waymore.py",
    "script": "others/waymore.sh",
    "category_slug": "others",
    "git_repo": "https://github.com/xnl-h4ck3r/waymore",
    "short_desc": "Find way more from the Wayback Machine!"
  }
}
```
