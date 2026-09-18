# Walkthrough report template

Use Markdown unless the user requested another format. Keep evidence in a stable sibling directory when files are available.

```markdown
# Software walkthrough report

## Decision

- Readiness: ready / ready with risks / not ready / blocked
- Target: build, URL, app version, or commit
- Platforms: device, OS, browser, viewport, locale
- Scope: journeys covered and exclusions
- Summary: concise release recommendation

## Coverage

| Area | Status | Notes |
|---|---|---|
| Page/window size | pass/fail/blocked/N/A | |
| Top/bottom regions | | |
| Scrolling | | |
| Buttons/clicks | | |
| Input fields | | |
| Dialogs/overlays | | |
| Routes/back | | |
| Images/video | | |
| Login/payment/share | | |
| Exceptional states | | |

## Findings

| ID | Severity | Confidence | Scope | Finding | Evidence |
|---|---|---|---|---|---|

### W-001: Short defect title

- Severity / confidence / scope:
- Environment:
- Preconditions:
- Steps to reproduce:
  1. ...
- Expected:
- Actual:
- User impact:
- Evidence:
- Diagnostic clues:
- Suggested fix direction:
- Regression candidate: yes/no, with the stable assertion to preserve

## Blocked and untested

- Check, blocker, and what is needed to complete it

## Automation follow-up

- Existing tests reused
- High-value scenarios to automate
- Tool choice and why
- Avoided automation and why
```

## Evidence rules

- Name files with finding ID, platform, and state, for example `W-003-ios-login-error.png`.
- Redact tokens, personal data, payment data, private URLs, and unrelated screen content.
- A screenshot proves visible state, not causality. Pair it with reproduction steps and diagnostics.
- Preserve console, network, trace, and audit artifacts only when they materially support a finding.
- Report generated-tool warnings separately from confirmed product defects.
