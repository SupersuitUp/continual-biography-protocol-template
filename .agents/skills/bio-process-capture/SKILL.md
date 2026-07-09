---
name: bio-process-capture
description: File and decompose a new capture (interview transcript, self-capture session, voice memo) into the biography's layers, then update STATE.md. Use when a new session recording or transcript arrives, when the biographer says "process this capture", or when any capture has processed:false.
---

# Process Capture

Phase 3 of the loop in [`AGENTS.md`](../../../AGENTS.md). Input: one raw transcript or recording. Output: the capture filed, every layer it touches updated with source links, `STATE.md` current, `processed: true`.

## Steps

1. **File it.** `captures/YYYY-MM-DD-<topic-slug>.md` with the frontmatter from `AGENTS.md` (`date`, `mode`, `participants`, `eras`, `processed: false`). Verbatim; never clean up the subject's words.
2. **Chronology.** Extract every dateable event. Add each under its era in `chronology.md` with the next event ID, a one-line summary, and a link to this capture. Uncertain dates get `circa`. If an event contradicts an existing one, keep both lines, tag `⚠ contradicts E<id>`, and log the contradiction in `STATE.md`.
3. **People.** Create or update one file in `people/` per person mentioned. Stub on first mention; grow on recurrence. Add open questions the mention raises.
4. **Themes.** Append dated, source-linked evidence bullets to existing theme files. Create a new theme file only when roughly three captures now touch the through-line.
5. **Quotes.** Copy voice-carrying lines verbatim into `quotes.md`, dated and source-linked.
6. **Media.** Log anything received in `media/INDEX.md` (date depicted, what it shows, events attested, provenance, rights). Emit new media asks into `STATE.md` for anything the session implied should exist.
7. **Projections.** Tag beats that clearly serve a target artifact into that projection's brief in `projections/` (a paintable image, a cinematic scene, a chapter seed).
8. **STATE.md.** Retire answered threads, open new ones, update gaps and contradictions, refresh the *Last updated* line.
9. **Flip the flag.** Set the capture's `processed: true` only when steps 2 through 8 are done.

## Rules

- The capture file is sacred after landing: corrections happen in the layers, never by editing the record.
- Every extracted event, fact, and quote carries a link back to this capture. Unlinked claims do not exist.
- Respect `SUBJECT.md` ground rules while filing (off-limits topics, third-party handling).
