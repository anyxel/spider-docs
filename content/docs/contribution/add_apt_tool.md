---
title: "APT Tool"
description: ""
summary: ""
date: 2024-01-31T14:41:26+06:00
lastmod: 2024-01-31T14:41:26+06:00
draft: false
menu:
  docs:
    parent: ""
    identifier: "add_apt_tool-d7e45cd6572632e0523d4309b5ffacf4"
weight: 54
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

We are using Ubuntu OS. You can install any tools using `apt`.

## Script

```bash {title="tools/scripts/igt/nmap.sh"}
#!/bin/bash

# Include shells
source ./tools/scripts/config.sh

echo "Installing nmap..."
apt install nmap -y

echo_green "Successfully installed!"
```

## Fixture


```json {title="tools/fixtures/tools/igt.json"}
{
  "model": "tools.tool",
  "pk": null,
  "fields": {
    "name": "Nmap",
    "lang": "",
    "directory": "",
    "run": "nmap",
    "script": "igt/nmap.sh",
    "category_slug": "igt",
    "git_repo": "https://github.com/nmap/nmap"
  }
}
```
