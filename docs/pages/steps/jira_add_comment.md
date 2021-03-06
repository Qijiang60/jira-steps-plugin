---
title: jiraAddComment
tags: [steps]
keywords: steps, comment
summary: "More about jiraAddComment step."
sidebar: jira_sidebar
permalink: jira_add_comment.html
folder: steps
---

## Overview

Add comment to the given issue.

![Comment](https://raw.githubusercontent.com/ThoughtsLive/jira-steps/master/docs/images/jira_add_comment.png)


## Fields

* **idOrKey** - Issue id or key.
* **comment** - comment, supports jira wiki formatting.
* **site** - Optional, default: `JIRA_SITE` environment variable.
* **failOnError** - Optional. default: `true`.

## Examples

* With default [site](config#environment-variables) from global variables.

  ```groovy
  node {
    stage('JIRA') {
      jiraAddComment idOrKey: "TEST-1", comment: "test comment"
    }
  }
  ```
* `withEnv` to override the default site (or if there is not global site)

  ```groovy
  node {
    stage('JIRA') {
      withEnv(['JIRA_SITE=LOCAL']) {
        jiraAddComment idOrKey: "TEST-1", comment: "test comment"
      }
    }
  }
  ```
* Without environment variables.

  ```groovy
    jiraAddComment site: "LOCAL", idOrKey: "TEST-1", comment: "test comment"
  ```

{% include links.html %}
