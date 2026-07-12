# Overnight task: take the existing guide from v0 to a polished public release

## Start here

Read `AGENTS.md`, `README.md`, and the complete `index.html` before changing anything. This repository already contains a working v0. Improve it in place; do not replace it with a framework, build system, dependency, or multi-file app.

The finished artifact is a single self-contained interactive HTML guide called **“How This Page Was Built — Through The Years.”** It teaches a total beginner how the same tiny to-do list would have been built in six eras, while the page itself acts as the modern live specimen.

## Non-negotiable constraints

- Keep the shipped experience in one `index.html`, with all CSS and JavaScript inline.
- Use no external scripts, fonts, CDNs, images, analytics, storage, or network calls.
- Keep exactly one running example: a text input, Add button, list, and checkboxes.
- Preserve the six stops: 1996 static HTML; 2002 PHP/CGI server rendering; 2006 jQuery + AJAX; 2013 AngularJS/Backbone SPA; 2016 React + webpack; 2024 React + Vite + TypeScript.
- Keep the scrubber keyboard-accessible and ensure code overflow stays inside code boxes. The page itself must never scroll horizontally.
- Support light and dark themes, narrow mobile screens, reduced motion, visible focus, and readable contrast.
- Do not add any personal name, username, local path, private-project reference, identifying metadata, or fabricated usage claim.
- Do not add dependencies or install packages.

## Accuracy anchors

Do not invent dates. Preserve and correctly contextualize these anchors:

- Netscape held roughly 80% browser share in 1995.
- Internet Explorer was bundled with Windows and reached roughly 95%+ share by 2002.
- jQuery: 2006.
- AngularJS: around 2010. Angular 2’s incompatible rewrite: 2016, with a real trust cost.
- React: 2013. A 2016 React example should use the period-appropriate class-component style, not Hooks.
- Grunt: 2012. Gulp: 2013. webpack: around 2012 and representative of the bundler era.
- Vite: 2020.
- TypeScript won the browser-development typing race.
- Bun was acquired by Anthropic in December 2025; do not imply that this was true in the 2024 era.

## What to improve

Treat the current page as a strong v0 and make a judgment-led polish pass:

1. Read the full learner journey and remove jargon that lacks a one-line explanation.
2. Ensure every era answers both “Why would anyone do it this way?” and “What pain made people move on?”
3. Check that the HTML-generation pendulum, JavaScript layer, build-tool evolution, JavaScript-to-TypeScript story, and CSS aside are woven through the narrative rather than dumped as trivia.
4. Make the horizontal era control feel clear and intentional with mouse, touch, and keyboard. The code, explanation, winner chip, and tide must always agree.
5. Test the live to-do flow: Enter submits, blank items fail safely, long text wraps, checkboxes remain labeled, and nothing persists or leaves the browser.
6. Refine hierarchy, spacing, typography, code readability, and narrow-screen behavior without turning the page into a generic card dashboard or adding decorative effects that obscure the lesson.
7. Keep the AI-assisted coda honest: it is a new abstraction and feedback-loop layer, not an escape from architecture, testing, accessibility, security, or ownership.

## Teaching depth: use the real words, then make them understandable

Develop the explanations enough that a smart beginner leaves with a durable mental model, not just a timeline of brand names. Preserve the field’s real terms of art and framework names; do not replace them with vague metaphors. The first time a term appears, give it a short plain-English gloss in the sentence or immediately beside it.

The learner should understand these ideas by the end:

- **Static HTML**: a finished document already exists on the server. The browser receives and displays it.
- **Server rendering**: code on the server combines templates and saved data to produce the HTML for each request.
- **DOM (Document Object Model)**: the browser’s live, scriptable representation of the page. Explain why hand-editing it became tedious.
- **AJAX**: a background request that exchanges data without replacing the whole page. Explain the effect, not the acronym’s historical expansion.
- **SPA (single-page application)**: the browser loads an application shell, then JavaScript changes the visible interface and manages navigation.
- **Data binding**: framework machinery that keeps data and displayed HTML in sync; note why invisible two-way updates could become confusing.
- **State**: the current data that determines what the interface shows. Use the to-do array as the concrete example.
- **Component**: a reusable piece of interface with its related behavior. Show why React’s component/state model helped teams organize larger screens.
- **Build step**: work done before browser delivery—such as transforming, combining, checking, or optimizing source files.
- **Task runner versus bundler**: Grunt/Gulp automated lists of jobs; webpack followed imports and packaged an application’s connected files. Keep this distinction to one clear contrast.
- **Native ES modules**: the browser can directly understand JavaScript `import`/`export`, allowing tools such as Vite to do less work during development.
- **Type checking / TypeScript**: checking expected data shapes before code runs, then producing ordinary JavaScript for the browser.
- **Abstraction**: machinery that hides repetitive lower-level work. Tie the tide indicator to what developers gained and what complexity they accepted.
- **DX (developer experience)**: how fast and understandable the work feels to the people building and maintaining the site.

For every era, connect the terms to the exact same sequence:

1. A person enters a to-do and presses **Add**.
2. Identify where that event is handled: browser, server, or both.
3. Identify where the new item is stored for the example.
4. Identify who creates or updates the `<li>`: a person editing a file, the server, hand-written DOM code, jQuery, a framework, or React state.
5. State what the user experiences: manual update, full reload, background update, or client-side state change.
6. Name the real pain that made the next approach attractive.

The code samples should remain faithful and recognizable, but they are teaching excerpts rather than production applications. Prefer the smallest sample that reveals the era’s organizing idea. Add a short annotation only when the important line is otherwise easy to miss.

Avoid going into the weeds. Do not add package-install commands, configuration files, loader/plugin inventories, framework API surveys, browser-engine internals, database design, routing edge cases, hydration variants, or a comprehensive CSS history. Mention a detail only when it helps explain the Add action, the client/server pendulum, the abstraction tide, or why developers changed tools.

Aim for layered readability:

- A skimming beginner can follow the era title, “why,” pain, winner, and tide.
- A curious reader can understand the code sample and the glossary-level definitions.
- An experienced developer sees historically credible terminology and tradeoffs without mistaking the page for exhaustive documentation.

## Verification bar

Before shipping:

- Run JavaScript syntax and HTML/static checks available in the environment.
- Exercise the page in a real browser if the environment permits: add and check a to-do; move the scrubber by pointer and keyboard; verify Home/End and arrow behavior; inspect all six synchronized states.
- Check at desktop width and at 320–375 px. Confirm `document.documentElement.scrollWidth <= document.documentElement.clientWidth`; only code blocks may scroll horizontally.
- Check light and dark color schemes and reduced-motion behavior when possible.
- Inspect browser console errors and unexpected network requests when possible.
- Search all public files for personal names, usernames, absolute paths, external URLs, analytics, `fetch`, `XMLHttpRequest`, and storage APIs. Resolve every real privacy finding.
- Run `git diff --check` and review the complete diff.

If a browser or another verification surface is unavailable, do the strongest safe alternative and state the exact limitation in the build signoff and commit message/body. Do not claim a check you did not run.

## Required build signoff

Append a newest-first timestamped entry inside the visible **Build signoff** section of `index.html`. It should act like a TL;DR Git history and include:

- Local timestamp and timezone.
- Lead agent and exact model ID, if exposed.
- Every subagent: role, exact model ID if exposed, and its bounded contribution.
- What changed, what was verified, and any remaining limitation.

Do not guess model IDs. Write “runtime did not expose the exact model ID” when necessary. Do not include a human’s name, account name, machine path, or other identifying information.

## Shipping authority and finish condition

This file grants explicit authority for this one overnight run to edit the repository, commit the finished and verified work, and push directly to `origin/main`. Do not open a pull request, enable hosting, modify repository settings, add secrets, or touch any other repository.

Finish only when:

1. The existing page has received a substantive polish and QA pass.
2. All non-negotiable constraints still hold.
3. The privacy sweep is clean.
4. The visible build signoff is updated.
5. The final changes are committed with a concise message and pushed to `origin/main`.

If a blocking issue makes a safe push impossible, leave the repository unpushed and report the blocker precisely rather than weakening the constraints.
