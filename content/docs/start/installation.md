---
title: "Installation"
description: ""
summary: ""
date: 2024-01-30T22:38:00+06:00
lastmod: 2024-01-30T22:38:00+06:00
draft: false
menu:
  docs:
    parent: ""
    identifier: "installation-4e0d0e0f89f7decc11eaad4ae9193018"
weight: 3
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

## Prerequisite

Install [Docker](https://docs.docker.com/get-docker/) on your computer.

## Install

To install Spider `beta` version, run this command.:

```bash
docker run -d --restart always -p 8001:8000 -p 8282:8282 --name spider anyxel/spider:beta
```

Then, run this command:

```bash
docker exec -it spider nohup python terminal.py &
```

Finally, visit the URL for the first time:

[http://localhost:8001/setup](http://localhost:8001/setup)

Done. Visit the following URL and enjoy!

[http://localhost:8001](http://localhost:8001)
