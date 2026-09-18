---
name: software-walkthrough
description: Perform evidence-backed exploratory software walkthroughs across web, mobile, desktop, and mini-app interfaces. Use when the user asks for 软件走查, product QA, smoke testing, usability inspection, release acceptance, or cross-platform interaction checks; do not use as a substitute for a formal penetration test.
---

# Software Walkthrough

Inspect the product like a careful first-time user, then turn observations into reproducible engineering evidence. Match the user's language in the report.

## Establish the test boundary

Identify the target build, platform, environment, critical user journeys, available accounts, and any operations that must not be completed. If the user did not specify them, infer the smallest safe scope from the product and state the assumption.

Read the repository before acting when source is available. Check its guidance files, manifests, existing E2E setup, test fixtures, and CI. Reuse the existing stack instead of adding a parallel framework. A request to inspect or report does not authorize dependency installation, production data changes, purchases, messages, publishing, or destructive actions.

Choose a platform route:

- Web or Electron renderer: use an available browser-control tool for exploration. Prefer existing Playwright tests for repeatable checks.
- iOS or Android: use an available simulator/device workflow. Prefer existing Maestro or Appium coverage when present.
- Native desktop: use native UI control and platform accessibility state; use Appium only when the project already supports the relevant driver.
- WeChat or another mini-app: use its official developer-tool workflow when available. Otherwise perform a manual UI walkthrough and clearly mark checks that could not be automated.

Read [references/checklist.md](references/checklist.md) before running a full walkthrough. Read [references/tooling.md](references/tooling.md) only when selecting or integrating automation. Read [references/report-template.md](references/report-template.md) before producing the final artifact.

## Run the walkthrough

1. Confirm the build is reachable and record the platform, viewport/device, locale, account state, network condition, and version or commit when available.
2. Map the visible product into primary journeys and state transitions. Prioritize authentication, navigation, core value delivery, data persistence, and recovery paths over exhaustive clicking.
3. Run one clean happy path before edge cases. Observe loading, empty, error, offline/slow, permission-denied, and expired-session states where safe and feasible.
4. Cover the ten Demo-derived dimensions in the checklist. Mark each item `pass`, `fail`, `blocked`, or `not applicable`; never silently omit an untestable item.
5. For every suspected issue, reproduce it once from a known state. Capture the smallest useful evidence: screenshot or recording, exact steps, expected versus actual behavior, environment, console/network clues, and relevant source location when known.
6. Distinguish product defects from environment failures, access-control problems, test-data problems, and subjective design suggestions.
7. Run automated audits only when they add signal. Treat Lighthouse and axe results as leads that require triage, not as automatically valid product bugs.
8. Re-test critical failures after a safe recovery action. Do not keep retrying an irreversible or externally visible action.

## Classify findings

Use severity based on user impact and reach:

- `S0 blocker`: prevents the product or a critical release path from being used broadly.
- `S1 critical`: breaks a core journey, risks data loss, or has no practical recovery.
- `S2 major`: materially harms a common journey but has a workaround.
- `S3 minor`: localized usability, visual, accessibility, or consistency problem.
- `S4 suggestion`: improvement without a demonstrated defect.

Also assign confidence (`high`, `medium`, `low`) and scope (`systemic`, `flow`, `screen`, `component`). Do not inflate severity because an issue is visually obvious.

## Deliver the result

Lead with release readiness and the highest-risk findings. Include a coverage matrix, issue list, evidence links, blocked checks, and recommended next actions. Separate confirmed defects from hypotheses. When source is available, link to exact files and lines; do not modify the product unless the user requested fixes.

Recommend automation candidates only for stable, valuable, repeatable flows. Prefer a thin regression layer over converting every exploratory observation into a brittle test.
