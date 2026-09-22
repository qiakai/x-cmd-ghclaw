# x-cmd/ghclaw — `ghclaw` landing page

`ghclaw` is a "claw design" for **GitHub events** — a folder-
based event listener that picks up GitHub events as files and
routes them through AI-assisted triage, comment, and reply
actions.

> 🌐 **中文版：[README.cn.md](./README.cn.md)** — same content,
> Chinese front matter.

This repo hosts the canonical landing-page documentation for
`ghclaw` — what it is, how the claw design works, and how to
plug in your own handlers. Articles are content-only and open
for **modification PRs** from anyone — see
[`CONTRIBUTING.md`](./CONTRIBUTING.md).

## What's in this repo

```
x-cmd/ghclaw/
├── README.md                 # this file (English)
├── README.cn.md              # Chinese version
├── CONTRIBUTING.md           # article workflow + frontmatter spec
├── SKILL.md                  # AI-agent recipe
├── LICENSE                   # Apache-2.0
└── docs/
    ├── 0-ghclaw-landing.{en,cn}.md    # the landing page
    ├── 0-ghclaw-landing.llms.md
    └── 0-ghclaw-landing.faq.yml
```

`docs/0-ghclaw-landing.{en,cn,llms,faq}.{md,yml}` is the
canonical four-file landing-page set. The leading integer
(`0-`) is the reading order; later slots (1-, 2-, …) can be
added for deeper topics (custom handlers, GitLab/Gitea
variants, deployment recipes).

## Sister repos

- [`x-cmd/cve`](https://github.com/x-cmd/cve) — topic library pattern reference.
- [`x-cmd/terminal`](https://github.com/x-cmd/terminal) — terminal topic library.
- [`x-cmd/browser`](https://github.com/x-cmd/browser) — browser topic library.
- [`x-cmd/x-cmd`](https://github.com/x-cmd/x-cmd) — module source (`mod/ghclaw/`).
- [`x-bash/ghclaw`](https://github.com/x-bash/ghclaw) — the source-level reference.

## License

Apache License 2.0 — see [`LICENSE`](./LICENSE).