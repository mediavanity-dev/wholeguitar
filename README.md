# Fretboard

Learn the guitar neck by playing it: the app asks, you play, the microphone checks. Live at **https://mediavanity-dev.github.io/fretboard/**.

## Where things are

| What | Where |
|---|---|
| Code (local) | `C:\Users\media\Desktop\dans stuff\Development\ClaudeGuitarTeacher` |
| Code (GitHub) | https://github.com/mediavanity-dev/fretboard (public, account `mediavanity-dev`) |
| Hosting | GitHub Pages, from `main` / root. Tracked on the [dashboard](https://mediavanity-dev.github.io/dashboard/). |

## What it teaches

One linear path. Each stage opens when 90% of the one before is learned.

| Stage | Cards | You play |
|---|---|---|
| 1. Notes | 70 | landmarks first: the open strings, then strings 6 and 5 at the marked frets, the notes between, sharps and flats, then strings 1, 4, 3 and 2 by octave shape, then "sweeps" (one note on every string) |
| 2. Octaves | 10 | the octave above or below a shown note |
| 3. Intervals | 66 | an interval (♭2 to 7) above a shown root |
| 4. Triads | 48 | major, minor, diminished and augmented triads, every inversion, every string set, low to high |
| 5. Scales | 18 | the seven modes and both pentatonics, one octave up |
| 6. Chords | 10 | seventh, sixth and suspended chords, spelled from the root |
| 7. Harmony | 14 | the diatonic triads and sevenths of a major key, by Roman numeral |
| 8. Ear | 20 | an interval or chord quality you hear |
| 9. Rhythm | 12 | quarters to sixteenths at 60, 90 and 120 bpm, scored by spread in ms |

Sight reading and technique are left out on purpose.

## How it works

| File | Purpose |
|---|---|
| `index.html` | The whole app: curriculum, spaced repetition, pitch detection (YIN), onset detection (AudioWorklet), fretboard (SVG) |
| `sw.js`, `manifest.webmanifest`, `icon*` | Installable and works offline |

- **Answers** are notes, detected from the microphone. A note counts once it's stable for about 100 ms. Sequences (triads, scales, chords) are played one note at a time.
- **Memory** is a Leitner schedule (5 min, 1, 3, 7, 16, 35, 90 days). A fast, correct answer moves a card up a box, a slow one moves it down one, and a miss sends it back to the start. "Learned" means box 2 or higher, "known" means box 4 or higher.
- **Progress** is kept in the browser's `localStorage` (`fretboard.v1`), with no account.
- **Analytics** use the shared GA4 tag (`G-FGFP95J3W9`), the same one as the other sites.

Run locally with any static server (the microphone needs `localhost` or https), e.g. `npx serve .`.
