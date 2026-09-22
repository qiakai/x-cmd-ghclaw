# Contributing — `x-cmd/ghclaw`

This page covers how to add or modify an article in the
`ghclaw` landing-page repo.

**Looking to read?** See [`README.md`](./README.md) for the
overview, or [`docs/0-ghclaw-landing.en.md`](./docs/0-ghclaw-landing.en.md)
for the landing page.

## Article slots

| Slot | Article | Add a new one? |
| --- | --- | --- |
| `0-ghclaw-landing` | The landing page — what `ghclaw` is, the claw design, how to use it. | Refresh in place; do not add a second `0-` slot. |
| `1-…`, `2-…`, … | Optional follow-up topics (custom handlers, GitLab/Gitea variants, deployment recipes). | **Yes** — open a PR with a new 4-tuple slot. |

## Per-slot file convention

Every article slot is **four files, kept in sync**:

| File | Purpose | Required? |
| --- | --- | --- |
| `n-<slug>.en.md` | Canonical English article. The one the GitHub social preview and search engines see. | ✅ |
| `n-<slug>.cn.md` | Chinese translation. Same structure, same anchors, same diagrams. | ✅ |
| `n-<slug>.llms.md` | LLM-friendly summary — YAML frontmatter + flat prose. | ✅ |
| `n-<slug>.faq.yml` | Structured Q&A used for the FAQ section and JSON-LD on the site. | ✅ |

If you change `.en.md`, change `.cn.md` in the same commit.

## Editing rules

- **One slot per commit.** Don't mix the landing page with a
  follow-up deep dive.
- **Both languages in the same commit.**
- **Quote from the official source (`x-bash/ghclaw`) only.**
  Don't paraphrase from third-party blogs without verifying
  against the upstream source.
- **Don't quote from `x-cmd-install/mneme`.** That repo is
  private.
- **Don't discuss intent.** Articles are content-only.

## CI

The site's build pipeline reads `docs/` and validates that:

1. Every `.en.md` has a matching `.cn.md` with the same
   filename stem.
2. Every slot has a `.llms.md` and a `.faq.yml`.
3. The `.faq.yml` is valid YAML and every `id` is unique.
4. The `.llms.md` frontmatter parses.

## What this repo is NOT

- **Not** the source code — that's
  [`x-bash/ghclaw`](https://github.com/x-bash/ghclaw) and
  [`x-cmd/x-cmd`](https://github.com/x-cmd/x-cmd) (mod/ghclaw/).
- **Not** an install database — that's
  [`x-cmd/install`](https://github.com/x-cmd/install).
- **Not** a substitute for the source-level docs.