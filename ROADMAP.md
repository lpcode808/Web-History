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

- Re-run the browser verification battery against HEAD. The final signoff entry (22:05 HST) states browser interaction and rendered viewport checks were not run for that pass because the available browser blocked local-file navigation; the last full headless-Chromium pass predates the final learner-journey changes.
- Real-device touch and mobile pass: scrubber drag, era-label taps, to-do flow on an actual phone.
- Light/dark and reduced-motion check in real browsers (headless checks exist for earlier revisions; confirm on HEAD in at least one real browser per scheme).
- Beginner reader test: have a novice read the page end to end and confirm they leave with the mental model the brief targets (HTML-generation pendulum, abstraction tide, why each era's pain drove the next).

## Constraints (do not relax)

See `AGENTS.md`. In short:

- Single self-contained `index.html`: inline CSS and JS, no external assets, dependencies, analytics, storage, or network calls.
- No personal names, usernames, machine paths, or private project references anywhere.
- Append a signoff entry to the visible "Build signoff" section after every substantial run; never guess model IDs.
- No commit or push without explicit approval.
