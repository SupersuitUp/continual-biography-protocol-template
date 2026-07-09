---
name: bio-intake-source
description: Intake a pre-existing source (manuscript, journal, letters, prior interview, photo batch) into the biography corpus and process it like a capture. Use during Phase B seeding of GENERATE.md, when the subject hands over old material, or when the STATE.md intake queue is non-empty.
---

# Intake Source

The seeding engine ([`GENERATE.md`](../../../GENERATE.md) Phase B) and the ongoing intake path for material that arrives mid-project.

## Steps

1. **File the raw material** into `sources/` (or, for prior chat-app capture sessions, into `captures/` with `mode: self-capture`). Name by the material's own date if it has one, the intake date if not. Photos and video go to `media/` with rows in `media/INDEX.md`.
2. **Sanitize first (biographer-run mode).** Before anything enters the repo, strip what is not the subject's own story: third-party confidences, the biographer's private notes, anything the biographer would not hand the subject tomorrow. The transferability rule in `AGENTS.md` is absolute.
3. **Add the source to the `STATE.md` intake queue**, then process from the queue largest-first.
4. **Process each source** with the same decomposition as `bio-process-capture` steps 2 through 8: events to `chronology.md` (new eras often get discovered here), people, themes, quotes, media asks, projection beats, STATE updates.
5. **Remove the source from the intake queue** when fully processed.

## Rules

- Intake, never homework: filing the raw material comes first; transcription and processing happen opportunistically, priority-ordered by `SUBJECT.md`.
- Do not summarize a source instead of processing it. A summary is not an event list; every extracted event carries its source link.
- Long sources process in passes: chronology first (the spine), then people and themes, then quotes. Note partial progress in the intake queue entry.
