---
title: "Post: Cloud Functions Deploy"
excerpt_separator: "<!--more-->"
categories:
  - GCP
tags:
  - Cloud Functions
  - Cloud Build
  - Deploy
---

Objective: Create a Cloud Function and deploy it using Cloud Build.

1. Create a function that will be started by a create event on Cloud Storage.
    ```yaml
    excerpt_separator: "<!--more-->"
    ```
2. Create a yaml to deploy it on dev and prod.
3. Create two branches: develop and main.
4. Create two triggers on Cloud Build. One for develop and other for main branch.
5. Test it pushing develop and main branch.