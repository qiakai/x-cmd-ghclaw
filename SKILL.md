---
name: ghclaw
description: ghclaw — a claw design for GitHub events. Folder-based event listener that picks up GitHub events as files and routes them through AI-assisted triage, comment, and reply actions. Use when the user asks about "ghclaw", "GitHub event listener", "AI-assisted GitHub triage", or "claw design".
metadata: type=landing-page, source=team-curated, schema=4-tuple-md, refresh=manual, license=apache-2.0, scope=ghclaw-design
---

# x-cmd/ghclaw — using the landing page

## 1. Read on the website

The landing page is published at <https://x-cmd.com/ghclaw>.

## 2. Use the raw files

Plain markdown + YAML, served over HTTPS from GitHub. Fetch
directly from `https://raw.githubusercontent.com/x-cmd/ghclaw/main/...`
— do not route through any CDN or proxy.

```sh
curl -fsSL "https://raw.githubusercontent.com/x-cmd/ghclaw/main/docs/0-ghclaw-landing.en.md"
```

## Article schema

This repo's primary article is the landing page. It follows
the same 4-tuple convention as other topic libraries:

| File | Shape | Purpose |
| --- | --- | --- |
| `0-ghclaw-landing.en.md` | Markdown with YAML frontmatter. | Canonical English landing page. |
| `0-ghclaw-landing.cn.md` | Same as above, in Chinese. | Chinese translation. |
| `0-ghclaw-landing.llms.md` | YAML frontmatter + flat structured sections. | LLM-friendly summary. |
| `0-ghclaw-landing.faq.yml` | Bilingual Q&A with `confidence` and `reference`. | FAQ + JSON-LD. |

## What `ghclaw` is

`ghclaw` is a "claw design" — a folder-based event listener
pattern for **GitHub events**. GitHub events arrive as files
in a watched folder (`$folder/<owner>/<repo>/event.txt`),
and `ghclaw` picks them up, classifies the event type
(`issue#comment`, `issue#created`, `pr#*`, etc.), and routes
each event to AI-assisted handlers via `x chat`, `x pi`, or
`x codex`. Replies and notifications are sent back via the
`x weixin` channel.

The "claw" metaphor: each event is grabbed by a *claw* that
sorts it, classifies it, and either drops it, replies to it,
or escalates it.

## Sources

- <https://github.com/x-cmd/ghclaw> — this repo (landing page docs).
- <https://x-cmd.com/ghclaw> — published landing page.
- [`x-cmd/cve/SKILL.md`](https://github.com/x-cmd/cve/blob/main/SKILL.md) — parallel topic-library pattern.
- [`x-cmd/terminal/SKILL.md`](https://github.com/x-cmd/terminal/blob/main/SKILL.md) — parallel topic-library pattern.
- [`x-cmd/browser/SKILL.md`](https://github.com/x-cmd/browser/blob/main/SKILL.md) — parallel topic-library pattern.
- [`x-bash/ghclaw`](https://github.com/x-bash/ghclaw) — source-level reference.