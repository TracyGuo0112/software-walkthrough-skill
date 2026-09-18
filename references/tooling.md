# Open-source tooling routes

Prefer tools already present in the repository. Inspect manifests and configuration before proposing installation. If no automation stack exists, keep the walkthrough manual unless the user asks to add one.

## Web and Electron

### Playwright

Repository: <https://github.com/microsoft/playwright>

Use for repeatable browser journeys, mobile emulation, screenshots, videos, traces, console/network capture, and Chromium/Firefox/WebKit coverage. Prefer `@playwright/test` for a repository test suite and resilient role, label, or test-id locators. Reuse saved authentication state only when the project already handles it securely; never commit session files.

### axe-core

Repository: <https://github.com/dequelabs/axe-core>

Use for automated accessibility checks after relevant UI states are visible. Re-run after opening menus, dialogs, and dynamic regions. Treat `incomplete` results as manual-review items, and supplement automation with keyboard, focus, zoom, and screen-reader-oriented inspection.

### Lighthouse

Repository: <https://github.com/GoogleChrome/lighthouse>

Use for repeatable performance, accessibility, best-practice, and SEO signals on representative public or locally served pages. Record the tested URL, device mode, throttling, and warnings. Do not compare scores from materially different environments as if they were equivalent.

### BackstopJS

Repository: <https://github.com/garris/BackstopJS>

Use when the project needs deterministic visual regression across stable routes and viewports. Establish reviewed baselines; do not approve a new baseline merely to remove a failure. Prefer targeted component or page scenarios over a large brittle screenshot catalog.

## Mobile

### Maestro

Repository: <https://github.com/mobile-dev-inc/Maestro>

Use for concise iOS/Android UI flows when the app can be launched in a simulator or device and the repository already uses Maestro, or when the user asks to establish mobile E2E coverage. Keep flows centered on user-visible state and stable identifiers.

### Appium

Repository: <https://github.com/appium/appium>

Use when the product needs WebDriver-based automation across native, hybrid, mobile web, or supported desktop drivers. Prefer it for an existing Appium codebase or a heterogeneous device lab; it is usually heavier than needed for a single lightweight walkthrough.

## Selection guide

| Need | Preferred route |
|---|---|
| Exploratory inspection only | Available browser/native UI control |
| Web regression flow | Playwright |
| Web accessibility findings | axe-core plus manual checks |
| Web performance baseline | Lighthouse |
| Stable pixel/layout comparison | BackstopJS or existing Playwright snapshots |
| Lightweight iOS/Android flows | Maestro |
| Existing cross-platform WebDriver lab | Appium |

Do not run all tools by default. Choose the smallest combination that answers the user's release question.
