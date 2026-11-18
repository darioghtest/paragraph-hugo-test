---
title: "Preview environments for every pull request"
date: 2026-10-09T09:00:00Z
description: "Harbor now spins up a full copy of your app for each pull request and tears it down when the branch merges."
tags: ["release", "deploys"]
draft: false
---

Reviewing a change is easier when you can click through it. Starting today, Harbor creates a preview environment for every pull request in a connected repository.

## How it works

Each preview gets its own URL, its own database branch, and the same environment variables as staging. When the pull request merges or closes, Harbor deletes the environment and its data.

## Limits

Previews sleep after an hour without traffic and wake on the next request. Each workspace can run up to twenty at once on the Team plan.
