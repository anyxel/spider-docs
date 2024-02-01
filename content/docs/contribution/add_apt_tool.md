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
weight: 55
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
source ./core/scripts/libs/config.sh

if command -v nmap &> /dev/null
then
    echo_yellow "Nmap is already installed!"
else
    echo "Installing Nmap..."
    try apt install nmap -y
    echo_green "Successfully installed!"
fi
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
    "git_repo": "https://github.com/nmap/nmap",
    "short_desc": "Nmap - the Network Mapper"
  }
}
```
