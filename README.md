# Software Walkthrough Skill

面向 Codex 的证据化软件走查 Skill，用于 Web、移动端、桌面端和小程序的探索式 QA、冒烟测试、体验验收与发布检查。

它将产品走查拆分为十个维度：页面尺寸、顶部与底部、滚动、按钮与点击、输入框、弹窗与浮层、路由返回、图片与视频、登录/支付/分享，以及异常状态。每项检查都会记录状态、证据、复现步骤、影响与建议。

## Features

- Runs a clean happy path before edge and recovery states.
- Produces reproducible findings with severity, confidence, scope, and evidence.
- Separates product defects from environment, access, and test-data failures.
- Supports Web, Electron, iOS, Android, native desktop, and mini-app workflows.
- Reuses an existing project test stack instead of introducing a parallel framework.
- Can route to Playwright, axe-core, Lighthouse, BackstopJS, Maestro, or Appium when those tools add useful signal.
- Avoids real purchases, public sharing, destructive actions, and sensitive-data capture unless explicitly authorized.

## Install

```bash
git clone https://github.com/TracyGuo0112/software-walkthrough-skill.git \
  "${CODEX_HOME:-$HOME/.codex}/skills/software-walkthrough"
```

Restart or reload Codex after installation if the Skill does not appear immediately.

## Usage

Invoke it explicitly:

```text
Use $software-walkthrough to inspect this web app and produce a release-readiness report.
```

```text
使用 $software-walkthrough 走查这个 iOS Demo，重点检查登录、路由返回和异常状态。
```

The Skill also supports automatic discovery for requests such as:

- “帮我做一次软件走查。”
- “检查这个版本能不能发布。”
- “Run a smoke test across mobile and desktop.”
- “Review this product flow and capture reproducible defects.”

## Output

A typical report includes:

- Release decision and tested environment
- Coverage matrix for the ten walkthrough dimensions
- Prioritized findings with reproduction steps and evidence
- Blocked or untested checks
- High-value regression automation candidates

## Open-source integrations

The Skill can work with existing project setups based on:

- [Playwright](https://github.com/microsoft/playwright) for browser flows, traces, screenshots, and cross-browser checks
- [axe-core](https://github.com/dequelabs/axe-core) for automated accessibility signals
- [Lighthouse](https://github.com/GoogleChrome/lighthouse) for Web performance and quality audits
- [BackstopJS](https://github.com/garris/BackstopJS) for stable visual regression scenarios
- [Maestro](https://github.com/mobile-dev-inc/Maestro) for lightweight mobile UI flows
- [Appium](https://github.com/appium/appium) for WebDriver-based cross-platform automation

These projects are not bundled or installed automatically.

## Repository structure

```text
.
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── checklist.md
    ├── report-template.md
    └── tooling.md
```

- `SKILL.md` contains the core workflow and decision rules.
- `references/checklist.md` defines walkthrough coverage.
- `references/tooling.md` routes automation choices.
- `references/report-template.md` defines the evidence-backed deliverable.
