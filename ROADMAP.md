# Roadmap

## Where things stand (2026-07-16)

The overnight polish run described in `OVERNIGHT_TASK.md` completed and was pushed on
2026-07-12 (eight commits, v0 through "Improve the learner journey" at HEAD). The
six-era interactive guide — one to-do example rebuilt from 1996 static HTML through
2024 React + Vite + TypeScript — is feature-complete per that brief. The site is
deployed and live on GitHub Pages (verified 2026-07-16, HTTP 200).

## Done

- Six synchronized eras: code excerpt, explanation, winner chip, milestone apps, request-path diagram, and abstraction-tide curve all track the scrubber together.
- Per-era "same Add, step by step" anatomy strip: where the event is handled, where the item lives, who writes the `<li>`, what the user sees.
- Plain-English first-appearance glosses for every term of art (DOM, AJAX, SPA, data binding, state, component, build step, ES modules, TypeScript, abstraction, DX).
- Bottom-of-page systems map covering hosting/CDNs, servers/APIs, data, identity, DNS, and operations.
- Three-persona learner critique integrated in the final pass: era labels are direct controls, every stop has a comparative "What changed" line, mobile reading order puts explanation before code, checkbox focus survives rerendering.
- Verified across passes: JS syntax checks, privacy grep sweeps, `git diff --check`, and (through the 18:04 UTC pass) headless-Chromium runs at 1280/340/320 px in light and dark with zero console errors, zero network requests, no horizontal overflow, working reduced motion, and full to-do and slider-keyboard flows.

## Next

- ~~Re-run the browser verification battery against HEAD.~~ Done 2026-07-19 (see the "real-browser verification pass" build signoff entry): a real headless-Chromium session against HEAD's `index.html` covered scrubber keyboard/mouse/touch control, the to-do flow, light/dark themes, reduced motion, zero horizontal overflow and console errors at 320/375/1280px, and zero non-`file://` requests. **Still open:** that pass could only reach the local file — this session's network egress policy blocked every attempt to open the actual live GitHub Pages URL (403 on CONNECT), so live-vs-HEAD parity remains unconfirmed since the 2026-07-16 check. Re-run against the live URL from an environment whose network policy allows it.
- Real-device touch and mobile pass: scrubber drag, era-label taps, to-do flow on an actual phone. Still open — Playwright touch/mobile emulation stood in for a real device in this pass (era-label taps and keyboard control confirmed reliable; native range-thumb drag did not register under emulation and needs a real device or real headed browser to check).
- ~~Light/dark and reduced-motion check in real browsers.~~ Done 2026-07-19 against HEAD: verified via computed styles (not just presence) that `prefers-color-scheme` swaps background/text colors and `prefers-reduced-motion: reduce` zeroes the tide-fill transition.
- Beginner reader test: still no real human novice has read the page. As a stand-in, a context-free agent cold-read the full six-era text on 2026-07-19 and reported that the pain-drives-next-era throughline held up, but surfaced two concrete polish candidates for a future content pass: (1) the "abstraction tide" line repeats identically across most eras and only reads as concrete by era six and the closing section; (2) each era's flow diagram uses a term (e.g. "DOM patch," "JSX") before the prose below it defines that term, so a linear reader meets the jargon first. Neither was corrected in this pass — verification only, no content edits made.

## Constraints (do not relax)

See `AGENTS.md`. In short:

- Single self-contained `index.html`: inline CSS and JS, no external assets, dependencies, analytics, storage, or network calls.
- No personal names, usernames, machine paths, or private project references anywhere.
- Append a signoff entry to the visible "Build signoff" section after every substantial run; never guess model IDs.
- No commit or push without explicit approval.
