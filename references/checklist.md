# Walkthrough checklist

Use this checklist as a coverage model, not a rigid script. Test the parts that exist and mark the rest `not applicable` or `blocked`.

## 1. Page and window size

- Check the supported viewport, orientation, zoom, safe area, display scaling, and minimum window size.
- Look for clipping, overlap, unexpected horizontal scroll, unreadable text, and controls outside the reachable area.
- On responsive products, cover one narrow, one representative, and one wide breakpoint unless the product defines a different matrix.

## 2. Top and bottom regions

- Verify headers, status/navigation bars, sticky elements, footers, tab bars, and home indicators.
- Confirm content is not obscured by fixed regions and that scroll-to-top/bottom states remain usable.

## 3. Scrolling

- Exercise short and long pages, nested scroll areas, infinite loading, refresh, keyboard scrolling, and scroll restoration where applicable.
- Watch for jumps, lost position, dead zones, duplicate fetches, and content that cannot be reached.

## 4. Buttons and clicks

- Check primary, secondary, destructive, disabled, loading, and repeated-click states.
- Verify hit targets, feedback, keyboard activation, focus order, debouncing, and idempotency.

## 5. Input fields

- Cover empty, valid, invalid, boundary-length, pasted, multilingual, and autofill values.
- Verify labels, validation timing, error recovery, keyboard type, focus visibility, submission behavior, and state persistence.
- Do not enter secrets or real personal data unless the user explicitly provided and authorized it for this target.

## 6. Dialogs and overlays

- Check open, close, cancel, confirm, outside click, Escape or system back, stacking, focus trapping, scrolling, and background interaction.
- Include dropdowns, tooltips, sheets, toasts, permission prompts, and loading masks.

## 7. Routes and back navigation

- Verify deep links, refresh, browser/system back, forward, tabs, redirects, authentication returns, and restoration after interruption.
- Confirm that unsaved state and protected routes behave intentionally.

## 8. Images, video, and media

- Check loading placeholders, aspect ratio, cropping, controls, captions, fallback states, large assets, slow network, and missing media.
- Verify alt text or equivalent accessible names when appropriate.

## 9. Login, payment, and sharing

- Cover signed-out, signed-in, expired-session, cancellation, duplicate submission, return URL, and permission-denied states.
- Stop before real purchases, messages, public sharing, or irreversible submissions unless specifically authorized.
- Never log credentials, tokens, payment data, or private share URLs in evidence.

## 10. Exceptional states

- Exercise offline or slow network, server errors, empty data, partial data, rate limits, permission denial, interrupted flows, and stale sessions when safe.
- Verify recovery guidance, retry behavior, data preservation, and whether the user can return to a known-good state.

## Cross-cutting checks

Apply throughout the ten dimensions:

- Accessibility: semantics, accessible names, keyboard/focus, contrast, text resizing, reduced motion, and assistive-technology announcements.
- Performance: first meaningful content, input response, layout stability, long tasks, excessive requests, and memory growth during repeated flows.
- Consistency: terminology, formatting, navigation patterns, disabled/loading behavior, and platform conventions.
- Privacy and security signals: unexpected data exposure, insecure transport warnings, over-broad permissions, and sensitive values in logs or URLs. Escalate to a dedicated security review for exploit validation.
- Localization: truncation, pluralization, date/number/currency formats, mixed languages, and right-to-left layout when in scope.
