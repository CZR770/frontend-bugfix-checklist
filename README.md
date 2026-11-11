# Frontend bug-fix checklist for small websites

A practical, free checklist for diagnosing one reproducible HTML, CSS, JavaScript, or React issue without accidentally breaking unrelated parts of a site.

**Scope:** Public-facing website behavior. This is not a vulnerability scan, accessibility certification, or guarantee of better search rankings.

## 1. Make the bug reproducible

- [ ] Record the **exact public URL**, device, browser, and approximate screen width.
- [ ] Write down the expected behavior and what actually happens.
- [ ] Note whether the problem is intermittent, logged-in-only, or reproducible in a private browser session.
- [ ] Capture a screenshot or short recording with customer details and private tokens removed.
- [ ] Confirm whether it started after a deployment, plugin update, or content change.

**Privacy:** Do not paste cookies, access tokens, passwords, customer records, or private URLs into public bug reports.

## 2. Find the smallest cause

- [ ] Open browser Developer Tools, reproduce the action, and check the **Console** for relevant errors.
- [ ] Check the **Network** panel for failed requests, wrong statuses, blocked CORS requests, or unexpected redirects.
- [ ] In **Elements**, inspect computed styles and the box model instead of blindly changing CSS.
- [ ] Verify all event handlers are bound to the intended interactive element.
- [ ] For React, check props, state updates, effect dependencies, stale closures, and console warnings.
- [ ] Compare against the last known good commit or deployment if available.

## 3. Test the user journey

| Area | Quick verification |
|---|---|
| Mobile layout | Check narrow widths (320–390 px), menu behavior, forms, horizontal overflow |
| Desktop | Test at a wide viewport; watch for broken alignment and missing navigation |
| Keyboard | Tab to interactive controls and confirm visible focus and expected activation |
| Forms | Check labels, validation, error states, and successful submission behavior |
| Navigation | Confirm expected routes, anchor targets, browser back, and no dead links |
| Network errors | Simulate an unavailable backend and verify a helpful, non-sensitive message |
| Performance | Compare real measurements before/after; do not confuse source heuristics with Core Web Vitals |
| Search basics | Check title, description, canonical, headings, and accidental `noindex` |

## 4. Make a narrow, reversible fix

1. Create a dedicated branch or backup.
2. Modify the smallest relevant component, stylesheet, or request handler.
3. Add or update a regression test when appropriate.
4. Run the project's formatter, linter, build, and relevant automated tests.
5. Check the broken flow manually on the appropriate devices and browsers.
6. Document changed files, root cause, test evidence, any limitations, and rollback steps.

## Request template

Copy this into an issue or brief **after removing private information**:

```text
Public page or feature:
Expected result:
Actual result:
Steps to reproduce:
Browser / device / viewport:
First noticed:
Console / network error (redacted):
Screenshots (redacted):
What has already been tried:
Definition of done:
```

## Need a developer to make the fix?

For clearly scoped frontend bugs, [book a fixed-price repair on Upwork](https://www.upwork.com/services/product/development-it-fast-fixes-for-html-css-javascript-and-react-website-bugs-2120592405683113639). Published options start at **$79** for one small issue; acceptance and scope are confirmed before work begins, and orders/payments stay on Upwork.

If you prefer to investigate a **public webpage** first, [try the free three-finding website preview](https://website-revenue-leak-audit.vercel.app/). It's a single-page automated heuristic check, **not** a manual legal, security, accessibility, or performance certification. The separate $495 full-audit checkout may not be available yet.

Custom-scoped web development and API integrations: [see the service descriptions](https://website-revenue-leak-audit.vercel.app/web-fix-services.html).

### Related official learning resources

- [MDN: Web development](https://developer.mozilla.org/en-US/docs/Learn_web_development)
- [web.dev: Performance](https://web.dev/learn/performance)
- [React: Debugging and troubleshooting](https://react.dev/learn)

This checklist is original educational material from Reznik LLC. It does not represent a customer testimonial or a claim of completed client work.
