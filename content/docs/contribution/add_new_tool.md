---
title: "Add New Tool"
description: ""
summary: ""
date: 2024-01-30T22:40:32+06:00
lastmod: 2024-01-30T22:40:32+06:00
draft: false
menu:
  docs:
    parent: ""
    identifier: "add_new_tool-6e304923208ef1858f2bef4355a625b3"
weight: 53
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

Adding a new tool is so easy. You can add any types of tools in Spider.

## Create Shell Script

Navigate to the `tools/scripts` directory, choose a category folder, and within that folder, create the script for your tool. This shell script should contain all the instructions for installing the tool.

Let's have a look at a Python based tool.

```bash {title="igt/sublist3r.sh"}
#!/bin/bash

# Tool
export tool_language="python"
export tool_directory="Sublist3r"
export branch_name="master"
export has_dependencies=true
export git_repo="https://github.com/aboul3la/Sublist3r"

# Install
source ./core/scripts/libs/install.sh
```

## Create Fixture

Now, go to `tools/fixtures/tools` directory. Then select/create a category file, example `igt.json` and insert the new tool data in the following format at the end of the file:

```json {title="igt.json"}
{
  "model": "tools.tool",
  "pk": null,
  "fields": {
    "name": "Sublist3r",
    "lang": "python",
    "directory": "Sublist3r", // Should be same as GitHub repository name
    "run": "sublist3r.py", // Main run file or command
    "script": "igt/sublist3r.sh", // Script path
    "category_slug": "others",
    "git_repo": "https://github.com/aboul3la/Sublist3r",
    "website": "",
    "short_desc": "Fast subdomains enumeration tool for penetration testers."
  }
}
```

Then, visit the URL to insert new tool to database:

[http://localhost:8001/setup](http://localhost:8001/setup)

Done. Visit the following URL and check:

[http://localhost:8001/tools](http://localhost:8001/tools)

After adding & testing the tool, create a [Pull Request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request).
