# Publishing Your Dataset Description as a Quarto Post

Your dataset description and EDA walkthrough should be published as a post on your Quarto site, not just kept in the notebook.

## 1. Create the post file

In your Quarto site repo, create a new file under `posts/`:

```
posts/dataset-eda/index.qmd
```

## 2. Add frontmatter

Every `.qmd` file starts with YAML frontmatter. Use this template:

```yaml
---
title: "<Your Dataset Name> — Exploratory Data Analysis"
description: "Dataset description and EDA for the <WaDi/EPIC> ICS dataset."
date: "2026-04-XX"
categories: [eda, graphids]
---
```

## 3. Write the post

The post should cover two things:

**Dataset description** — what the dataset is, where it comes from, what it contains. Use the template below as a starting point:

```markdown
## Dataset Description

**Name:**

**Source:** (link to original paper or project page)

**Domain:** (what real-world system does this monitor?)

**Size:** (rows, columns, file size)

**Features:** (group the columns — sensor readings, actuator states, timestamps, labels — you don't need to list every column)

**Label / Target:** (which column, how many classes, class balance)

**Attack Types:** (what kinds of attacks, brief description of each)
```

**EDA findings** — summarize what you discovered. Include your key charts (export from the notebook or embed the notebook directly) and 3-5 bullet points on what stands out.

## 4. Preview and publish

```bash
quarto preview    # check it locally
git add posts/dataset-eda/
git commit -m "Add dataset EDA post"
git push          # GitHub Actions deploys to Pages
```
