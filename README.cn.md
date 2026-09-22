# x-cmd/ghclaw — `ghclaw` 着陆页

`ghclaw` 是一种用于 **GitHub 事件** 的 "claw 设计"—— 基于文件夹
的事件监听器，将 GitHub 事件作为文件拾取，并路由到 AI 辅助的分类、
评论与回复动作。

> 🌐 **English version: [README.md](./README.md)** — same
> content, English front matter.

本仓库托管 `ghclaw` 的标准着陆页文档 —— 它是什么、claw 设计如何
工作、如何接入自定义处理器。文章为内容导向，欢迎任何人提交
**修改 PR** — 见 [`CONTRIBUTING.md`](./CONTRIBUTING.md)。

## 仓库结构

```
x-cmd/ghclaw/
├── README.md                 # 本文件（英文）
├── README.cn.md              # 中文版
├── CONTRIBUTING.md           # 文章写作流程 + frontmatter 规范
├── SKILL.md                  # AI agent 配方
├── LICENSE                   # Apache-2.0
└── docs/
    ├── 0-ghclaw-landing.{en,cn}.md    # 着陆页
    ├── 0-ghclaw-landing.llms.md
    └── 0-ghclaw-landing.faq.yml
```

`docs/0-ghclaw-landing.{en,cn,llms,faq}.{md,yml}` 是标准的四文件
着陆页集合。前缀数字（`0-`）是阅读顺序；后续槽位（1-、2-、……）可
用于更深的话题（自定义处理器、GitLab/Gitea 变体、部署配方）。

## 姊妹仓库

- [`x-cmd/cve`](https://github.com/x-cmd/cve) — 专题文库模式参考。
- [`x-cmd/terminal`](https://github.com/x-cmd/terminal) — 终端专题文库。
- [`x-cmd/browser`](https://github.com/x-cmd/browser) — 浏览器专题文库。
- [`x-cmd/x-cmd`](https://github.com/x-cmd/x-cmd) — 模块源码（`mod/ghclaw/`）。
- [`x-bash/ghclaw`](https://github.com/x-bash/ghclaw) — 源码级参考。

## 许可

Apache License 2.0 — 见 [`LICENSE`](./LICENSE)。