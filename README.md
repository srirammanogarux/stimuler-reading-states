# Stimuler · Reading-state outcomes

Prototype of the reading-state evaluation flows, now across three surfaces. Live at
[stimuler-reading-states.vercel.app](https://stimuler-reading-states.vercel.app), or open any page
locally. The **left-side "Surface" switcher** (on every page) moves between them; the
**right-side chips** switch the auto-scripted flows on each page.

## Surfaces

### `index.html` — Roadmap (unchanged)

The original roadmap prototype from `reading-state-spec.md`, built on the Figma "ideal" section
(Stimuler v2 · node 32234-49720):

- **Ideal · full read** — video lesson → scale-down into the reading state → live gold word
  highlights → green success, with **"Perfect" sliding in as a top notification** → clean
  scale-back into the video.
- **Retry · partial** — attempt 1 lands 4 of 7 words: matched words stay gold, missed drop to
  grey. The speaker replays the phrase karaoke-style, then the learner reads again and gets "Nice".
- **Deferred · 2 tries** — second attempt still short: card goes soft-peach, "Tricky one. Saved
  for later", bookmark pops as it fills.

### `chat.html` — Chat onboarding (india-onboarding `?step=reading`)

The reading test inside the chat onboarding, rebuilt pixel-faithfully from the india-onboarding
source (`data-theme="app"` tokens, glass read card, orb → pill → tick mic, "Well done !" banner),
with the new outcome states designed in Paper ("Designed" boards):

- **Ideal** — words fill **purple** live as the mic hears them → confirm → deep-green done card,
  "Well done !" banner. Exactly as shipped.
- **Retry** — partial read: heard words turn **green**, missed turn **dark amber**; the card warms
  up and its label swaps to "We didn't get it fully.. Try again!"; the speaker chip is nudged and
  the mic goes **inactive amber**. Tapping the speaker switches straight to the reset screen
  ("Let's speak again", purple mic) for a full second read.
- **Deferred** — try 2 still short: everything goes positive green. Banner: "No worries, we've
  noted it!" / "We will practice similar phrases later on, let's move forward"; card label:
  "Its okay! We will try later.."; heard words green, missed dim; flow moves forward.

### `form.html` — Form onboarding (usa-onboarding speaking task)

The `#acthint` reading scaffold rebuilt from the onboarding-form source, with a **Branch**
toggle — **Hint (int/adv)**: "Try reading this" + the cohort question and model answer;
**Beginner (direct)**: "Let's hear you speak" + the personalised affirmation. Same states in
both branches:

- **Ideal** — purple live fill, scaffold bar climbs 50→100% → all green, green wash, controls
  fade, "Finding your level…".
- **Retry** — eyebrow swaps to "WE DIDN'T GET THAT RIGHT, TRY AGAIN", screen washes warm, the
  progress fill runs indigo→amber, heard words green / missed dark amber, speaker tool nudged,
  mic inactive amber ("Listen & Try again") → speaker tap → reset screen → full second read.
- **Deferred** — eyebrow "NO WORRIES, WE'VE NOTED IT", bar completes, heard words green, missed
  dim, controls gone, "Finding your level…".

## Deep links

`index.html#retry` · `chat.html#deferred` · `form.html#retry` · `form.html#beginner-deferred` …

## Rules

Two tries max, whole passage as the unit, no red, no failure blocking, progression never stopped.
Reading is **purple live**; evaluation turns right words **green** and missed words **dark amber**;
deferral is always a **positive green** ending ("noted it"), never a failure state. Success paths
are exactly what the shipped onboardings do today. The original india/usa onboarding deployments
are untouched — everything lives in this repo.

Assets and visual system shared with `~/Desktop/Stimuler/language-settings/` (roadmap page) and
the india/usa onboarding token sets (chat/form pages: Geist + Inter, `#6C63FF` interactive,
`#9D96FF` live words, `#63E39B`/`#43D6A0` green, `#CF975E` dark amber).
