---
title: "How we cut median build times in half"
date: 2026-11-03T09:00:00Z
description: "A shared layer cache and smarter scheduling took our median build from 6 minutes to under 3."
tags: ["engineering", "performance"]
draft: false
---

Most builds on Harbor install the same dependencies their last build installed. We were throwing that work away every time.

## A shared layer cache

Builds now restore dependency layers from a cache keyed on the lockfile. When the lockfile hasn't changed, the install step finishes in seconds.

## Scheduling near the cache

We also route builds to the runner pool that already holds the warmest cache for that project. Together, the two changes took the median build from about six minutes to under three.
