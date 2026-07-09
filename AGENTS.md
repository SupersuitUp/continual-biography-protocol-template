# Operating instructions for agents

This repo is a **Continual Biography Protocol (CBP)** workspace: the version-controlled corpus of one person's life story. Your job is to make every interview session smarter than the last, keep the derived layers faithful to the raw captures, and grow the media library in lockstep with the story.

Read these three files before doing anything:

- [`README.md`](./README.md): what this repo is and the loop it runs.
- [`SUBJECT.md`](./SUBJECT.md): who this biography is about, who it is for, and the ground rules.
- [`STATE.md`](./STATE.md): the current open threads, gaps, contradictions, and next session guide.

## The loop you run

### 1. Prep (before every session)

Read `SUBJECT.md`, `STATE.md`, and skim `chronology.md`. Rewrite the **Next Session** section of `STATE.md` as a concrete guide:

- One era or theme of focus (pick the thinnest era or the hottest open thread).
- The top 3 to 5 open threads to pull, phrased as the questions a curious biographer would ask.
- Contradiction checks, phrased gently (present both versions, let the subject reconcile).
- Media asks to make in person ("bring the photo from the wedding year").

One question at a time in the session itself. Go deep before wide: when the subject mentions a person, place, or turning point, the follow-up beats the next scripted question.

### 2. Capture

The raw session record lands as `captures/YYYY-MM-DD-<topic-slug>.md` with this frontmatter:

```yaml
---
date: "YYYY-MM-DD"
mode: interview | self-capture | voice-memo | found-source
participants: [subject, biographer]
eras: []          # era slugs touched, filled at processing time
processed: false  # flipped true only when step 3 is complete
---
```

Capture rules: verbatim over polished, specifics over summaries, testimony over writing. **Never edit a capture after it lands.** Corrections happen in the layers, with the contradiction noted, never by rewriting the record.

### 3. Process (same day as capture)

Decompose the capture into the layers:

- **`chronology.md`**: add each new dated event (or "circa") under its era, with the next event ID and a link back to this capture. If a new event contradicts an existing one, keep both visible and log the contradiction in `STATE.md`.
- **`people/`**: create or update one file per recurring person mentioned. First mention gets a stub; recurring mentions grow the file.
- **`themes/`**: append evidence bullets to existing theme files. A new through-line earns its own file after roughly three captures touch it. Do not force themes; they are discovered, never imposed.
- **`quotes.md`**: copy lines worth preserving exactly, verbatim, dated, source-linked. These are voice-locked: never paraphrase them downstream.
- **`media/INDEX.md`**: log any media received (date, what it shows, which events it attests, provenance). Emit new media asks into `STATE.md` for photos or footage the session revealed should exist.
- **`projections/`**: if the session produced a beat that clearly serves a target artifact (a paintable image, a cinematic scene, a chapter seed), tag it in that projection's brief.
- **`STATE.md`**: retire answered threads, open new ones, log new gaps and contradictions, update the intake queue, and rewrite Next Session.

Flip the capture's `processed:` flag to `true` only when all of the above is done. A capture left unprocessed is debt; the Compound phase hunts for it.

### 4. Compound (periodic audit)

Every 5 to 10 captures, or monthly, run a coherence pass:

- Which eras are thin? (Compare `chronology.md` density per era.)
- Any captures with `processed: false`?
- Contradictions in `STATE.md` older than three sessions?
- Media asks pending longer than a month?
- Does `STATE.md` still fit on roughly one screen? If it has bloated, archive resolved material to the bottom of the relevant layer files.

Audit findings become interview fuel: write them into Next Session.

## Intake (pre-existing material)

Most subjects arrive with journals, manuscripts, photos, or prior interviews. File the raw material into `sources/` and run the same Process phase over each source as if it were a capture. The first `STATE.md` should be born already knowing the eras, the recurring people, and the gaps. Track unprocessed sources in the `STATE.md` intake queue.

## House rules

- **Raw truth is sacred.** Captures and sources are never edited, summarized in place, or "cleaned up."
- **Every event is source-linked.** A chronology row without a link to its attesting capture or source does not exist.
- **Contradictions stay visible** until an interview resolves them. Conflicting dates sit side by side.
- **Transferable to the subject on day one** (biographer-run mode). Only the subject's story, words, and people go in. Nothing the biographer holds in confidence from third parties, no operator strategy notes, nothing that would need redacting before handing the subject the repo.
- **Confidential by default.** This repo holds a real person's raw testimony. Do not share its contents outside the repo.
- **`STATE.md` stays short.** It is the one file read before every session. Threads, gaps, contradictions, asks, next session. Everything else lives in the layers.
- **No em dashes.** Use colons, parentheses, or separate sentences.
- **Sensitivities in `SUBJECT.md` are binding.** Off-limits topics stay off-limits; verbatim-preservation requests are honored; named third parties are handled per the ground rules.

## What "done" looks like for any session

The capture is filed with correct frontmatter, every layer it touches is updated with source links, new media asks and threads are in `STATE.md`, the Next Session guide reflects what was learned, and the capture's `processed:` flag is true.
