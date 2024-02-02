---
title: "Add New Category"
description: ""
summary: ""
date: 2024-01-31T13:43:09+06:00
lastmod: 2024-01-31T13:43:09+06:00
draft: false
menu:
  docs:
    parent: ""
    identifier: "add_new_category-2ed813f98929c964c1ad8bc57b110c30"
weight: 52
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

To add a new category, open the `tools/fixtures/category.json` file and insert the new category data in the following format at the end of the file:

```json {title="category.json"}
{
  "model": "tools.category",
  "pk": null,
  "fields": {
    "name": "New Category",
    "slug": "new-category"
  }
}
```

Then, visit the URL to insert new category to database:

[http://localhost:8001/setup](http://localhost:8001/setup)

Done. Visit the following URL and check:

[http://localhost:8001/tools](http://localhost:8001/tools)
