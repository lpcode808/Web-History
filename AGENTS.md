# Project instructions

This is a public, dependency-free, single-file teaching site.

- Keep the shipped experience in `index.html`: inline CSS and JavaScript, no external assets, fonts, scripts, analytics, storage, or network calls.
- Do not add personal names, usernames, machine paths, private project references, or identifying metadata.
- After every substantial agent run, append a compact entry to the visible “Build signoff” section in `index.html`. Include the local timestamp and timezone, lead model, each subagent model, role split, and what changed. If the runtime does not expose an exact model ID, say so; never guess.
- Keep entries newest-first. Treat them as a human-readable TL;DR history, not a replacement for Git history.
- Do not commit or push without explicit approval.
- `OVERNIGHT_TASK.md` carries explicit one-run approval to commit and push its completed, verified scope directly to `main`. That approval does not extend beyond the task described there.

## Open questions — `ASK.md`

<!-- ask-convention:v1-public — deliberately name-free and path-free; this repo is public and its
     rules above forbid personal names, machine paths, and identifying metadata. Do not replace this
     with the standard block. -->

When you hit a decision that is the maintainer's to make, and you can't resolve it from this repo,
the request, or a sensible default: append it to `ASK.md` at this repo's root (create the file if it
doesn't exist), then keep going on everything that doesn't depend on the answer.

    - [ ] YYYY-MM-DD · **The question, one sentence, in bold.**
          Context: why it came up. One or two lines.
          Options: (a) the one you'd pick and why (b) the real alternative
          Blocks: what's stalled — or "nothing, I proceeded with (a)"
          Asked-by: <harness>

Append at the bottom. Never delete, reorder, or check your own box. Always draft the options — a
question with no options is homework; a question with two named options and a recommendation is a
fifteen-second decision. Answers come back into this same file as checked items carrying an
`**Answer (date):**` line, so a later session reads them as settled rather than re-asking.

Ask sparingly — one or two real asks per session is a lot. Routine judgment calls, file moves,
cleanups, and merge conflicts are inside the assignment, not asks. If you could proceed under an
assumption, proceed under it and say which one you took.

`ASK.md` is subject to every privacy rule above: no personal names, no machine paths, no private
project references. If a question can't be asked without them, ask it somewhere other than this repo.
