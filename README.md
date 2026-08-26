# Stimuler · Reading-state outcomes

Prototype of the roadmap reading-state evaluation flows from `reading-state-spec.md`, built on the Figma "ideal" section (Stimuler v2 · node 32234-49720).

Open `index.html`. Right-side chips switch between auto-scripted flows:

- **Ideal · full read** — video lesson (dotted-underline interlinear subtitles) → scale-down into the reading state → live gold word highlights → green success, with **"Perfect" sliding in as a top notification** → clean scale-back into the video.
- **Retry · partial** — attempt 1 lands 4 of 7 words: matched words stay gold, missed words drop to grey. The speaker then replays the whole phrase karaoke-style (grey base, each word lighting white as it is read), then the learner reads again and gets "Nice" as a top notification.
- **Deferred · 2 tries** — same karaoke replay between attempts; the second attempt is still short, so the card goes soft-peach, the callout reads "Tricky one. Saved for later", and the bookmark button pops hard as it fills.

Deep-link a flow with a hash: `index.html#retry`, `#deferred`.

Copy rules: no em dashes anywhere, no red, no failure language, progression never blocked. Grade acknowledgements always arrive as the top notification, never inline on the card.

Assets and visual system shared with `~/Desktop/Stimuler/language-settings/` (Urbanist + Red Hat Display, gold/peach tokens, Sarah video).
