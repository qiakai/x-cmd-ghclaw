---
name: 0-ghclaw-landing
description: ghclaw — a folder-based event listener pattern for GitHub events. Each event is grabbed by a "claw" that classifies it (issue#comment, pr#opened, etc.) and routes to AI-assisted handlers via x chat / x pi / x codex. Replies go back via GitHub comment or x weixin.
type: summary
---

# Core Content

core_features:
  - Folder-based event listener for GitHub events
  - Four-piece claw design: watcher, classifier, handlers, notifier
  - AI handlers via x chat (general), x pi (issue-triage), x codex (PR review)
  - Notification channels: GitHub comment, x weixin, local queue, webhook
  - Replayable / debuggable via the events folder

# Key Information

highlights:
  - One watched folder; one classifier; many small handlers
  - Handlers are plain shell scripts; AI handlers pipe the event into x chat / x codex
  - Recognizes issue#created, issue#comment, issue#closed, pr#opened, pr#comment, pr#review, pr#merged, push, release, workflow_run, star, fork
  - Custom kinds via --on handlers
  - Latency is poll-interval or inotify-latency, not sub-second

# Use Cases

use_cases:
  - AI-assisted GitHub issue triage without writing a server
  - AI-assisted PR review-style comments
  - One watcher for every event type
  - Debug event flow by inspecting files
  - Plug in custom handlers without rebuilding the listener

# Architecture

components:
  watcher:
    role: Polls or subscribes to the watched folder
    impl: x-bash/ghclaw (mod/ghclaw)
  classifier:
    role: Parses filename and envelope into typed event
    output: kind (issue#comment, pr#opened, etc.) + payload
  handlers:
    role: One per event type
    examples:
      - issue-triage.sh: AI via x chat
      - issue-comment.sh: AI via x chat
      - pr-triage.sh: AI via x codex
      - pr-comment.sh: AI via x codex
  notifier:
    role: Sends handler reply back to upstream
    channels: [GitHub comment, x weixin, local queue, webhook]

# Related Resources

official:
  source: https://github.com/x-bash/ghclaw
  module: https://github.com/x-cmd/x-cmd (mod/ghclaw/)
related:
  - name: GitHub webhook events
    url: https://docs.github.com/en/webhooks/webhook-events-and-payloads
  - name: x chat
    url: https://x-cmd.com/mod/chat
  - name: x codex
    url: https://x-cmd.com/mod/codex

# Summary

ghclaw is a "claw design" for GitHub events — a folder-based event listener that picks up events as files, classifies them, and routes to AI-assisted handlers via x chat / x pi / x codex. The four-piece architecture (watcher, classifier, handlers, notifier) trades event-loop boilerplate for plausible file flow that's easy to debug, replay, and hand-test. Replies can flow back as GitHub comments, x weixin messages, local queue writes, or webhook posts. Use it for AI-assisted triage without writing a server; skip it if you need sub-second latency or a serverless-only deployment.