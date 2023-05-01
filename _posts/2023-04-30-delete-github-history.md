---
title: "Delete the whole commit history in Git/GitHub"
excerpt_separator: "<!--more-->"
tags:
  - git
  - github
  - tutorial
---

> **This will delete the whole commit history irrevocably**

## Create new orphan branch:

    git checkout --orphan temp_branch 

## Add all files to the new temp_branch and commit them:

    git add -A

    git commit -am "initial commit"

## Delete old main branch:

    git branch -D main

## Rename the temp_branch to main:

    git branch -m main

## Force push the changes to GitHub:

    git push -f origin main