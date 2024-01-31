---
title: "Prepare Environment"
description: ""
summary: ""
date: 2024-01-30T22:39:31+06:00
lastmod: 2024-01-30T22:39:31+06:00
draft: false
menu:
  docs:
    parent: ""
    identifier: "prepare_environment-e7b7ff32cd931ded140b146baf59b3da"
weight: 51
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

## Prerequisite

Install [Docker](https://docs.docker.com/get-docker/) and [Docker Compose](https://docs.docker.com/compose/install/) on your computer.

## Fork Project

Go to [Spider repository](https://github.com/anyxel/spider) and fork it.

Clone the project from GitHub:

```bash
git clone git@github.com:YOUR_USERNAME/FORKED_REPO.git
```

Create a new branch:

```bash
# Structure
git checkout -b add-toolname-tool

# Example
git checkout -b add-nmap-tool
```


Open the project in your IDE. Now run the project.

## Run Project

The project is developed with [Django](https://www.djangoproject.com/). You can run the project using Docker or by creating a Python virtual environment.

If you are using Windows, we recommend using Docker.

### Docker

Run this command:

```bash
docker compose -f docker-compose.dev.yml up -d
```

Project URL: [http://localhost:8001](http://localhost:8001)

Terminal PTY Server: [http://localhost:8282](http://localhost:8282)

### Python VEnv

Install [Python](https://www.python.org/) and set up [Virtual Environment](https://www.freecodecamp.org/news/how-to-setup-virtual-environments-in-python/).

Install requirements:

```bash
pip install -r requirements.txt
```

Now run:

```bash
python manage.py runserver
```

Project URL: [http://localhost:8000](http://localhost:8000)
