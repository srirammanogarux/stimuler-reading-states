# Stimuler · Reading-state outcomes

Prototype of the roadmap reading-state evaluation flows from `reading-state-spec.md`, built on the Figma "ideal" section (Stimuler v2 · node 32234-49720).

Live at [stimuler-reading-states.vercel.app](https://stimuler-reading-states.vercel.app), or open `index.html` locally. Right-side chips switch between auto-scripted flows:

- **Ideal · full read** — video lesson (dotted-underline interlinear subtitles) → scale-down into the reading state → live gold word highlights → green success, with **"Perfect" sliding in as a top notification** → clean scale-back into the video.
- **Retry · partial** — attempt 1 lands 4 of 7 words. The words that did not come through go **inactive**, the card border warms to golden brown, and the **mic goes to sleep and says why** ("You missed a few words") while the coach bubble steps out. Then the **speaker takes over**, replaying the phrase karaoke-style with the bubble carrying "Listen once, then read it again". Only when it finishes does the **mic wake up** with a ring and "Your turn". The second read lands and "Nice" arrives as a top notification.
- **Deferred · 2 tries** — same three beats after attempt 1. Attempt 2 is still short, so it goes **straight to saved**: no second "you missed" beat, since there is no third try to set up. The card goes soft peach, the bookmark pops as it fills, and **"Saved to your roadmap"** arrives as a peach notification.

The right-side checkbox toggles the **card fill variant**, where the whole card warms on a short read instead of the border alone.

Deep-link a flow with a hash: `index.html#retry`, `#deferred`.

Copy rules: no em dashes anywhere, no red, no failure language, progression never blocked.

Messaging rule: **notifications are for terminal outcomes only** (Perfect, Nice, Saved to your roadmap). Anything mid-attempt stays inline, carried by the mic tooltip, the coach bubble and the card colour, so the notification still means something when it arrives. Only one of those channels speaks at a time.

Assets and visual system shared with `~/Desktop/Stimuler/language-settings/` (Inter + Geist, gold/peach tokens, Sarah video).
