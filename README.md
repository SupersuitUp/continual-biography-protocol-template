# Continual Biography Protocol (CBP) workspace

A version-controlled home for one person's life story. The corpus compounds: every interview session is prepared from the repo's current state, every session is decomposed back into structured layers, and every artifact the life deserves (a memoir, a narrated site, a film, an art series) is a projection of the one corpus.

> ## ⚠️ Before You Fork
>
> This template is public. **Your fork should be private.** When you click "Use this template", set Repository Visibility to **Private** before creating the new repo. This repo will hold a real person's raw testimony, family history, and private memories.
>
> *If you forget, change visibility later in Settings → Danger Zone → Change visibility. Anything pushed while public is in the commit history; rotate anything sensitive that was exposed.*

## What this is

Most life-story projects die in one of two ways: the blank-page memoir that stalls on chapter one, or the drawer of disconnected interview transcripts nobody can navigate. This workspace replaces both with a boring, legible loop:

1. **Prep.** Before each session, the agent reads [`SUBJECT.md`](./SUBJECT.md) and [`STATE.md`](./STATE.md) and writes a session guide: what to focus on, which open threads to pull, which contradictions to check, which photos to ask for.
2. **Capture.** The interview happens and gets recorded. The raw transcript lands as a dated file in [`captures/`](./captures/), verbatim, never edited afterward.
3. **Process.** Same day, the capture is decomposed into the layers: events into [`chronology.md`](./chronology.md), people into [`people/`](./people/), through-lines into [`themes/`](./themes/), verbatim lines into [`quotes.md`](./quotes.md), media into [`media/`](./media/INDEX.md). Then `STATE.md` is updated so the next prep starts smarter.
4. **Compound.** Periodic audits find thin eras, unprocessed captures, and stale contradictions, and feed them back into the next session guide.

The interview reads the repo. The repo absorbs the interview. That closed loop is the whole method.

**Canonical doctrine:** [The Capture-First Autobiography](https://appliedai.wiki/playbooks/capture-first-autobiography). Capture the raw truth first, in files you own; transform later. This workspace is the operator-grade instrument for running that doctrine over months and years.

## Repo layout

```
<subject>-biography/
├── README.md          # this file
├── VERSION            # the CBP version this repo tracks
├── GENERATE.md        # bootstrap procedure: fork → configure → seed → first session
├── AGENTS.md          # operating instructions for any agent working in this repo
├── CLAUDE.md          # points Claude Code at AGENTS.md
├── SUBJECT.md         # purpose, audience, priorities, ground rules, sensitivities
├── STATE.md           # the compounding organ: threads, gaps, contradictions, next session
├── chronology.md      # the master event list, era by era, every event source-linked
├── quotes.md          # voice-locked verbatim registry
├── captures/          # raw dated session transcripts
├── sources/           # pre-existing raw material: manuscripts, journals, letters, scans
├── people/            # one file per recurring person in the subject's life
├── themes/            # one file per through-line
├── media/             # photos, video, audio + INDEX.md
└── projections/       # one brief per target artifact (book, site, film, ...)
```

## Who runs it

Two configurations, same repo shape:

- **Self-run.** The subject is the biographer. The agent interviews them directly, session by session.
- **Biographer-run.** An operator runs the corpus on behalf of a subject (a parent, an elder, a friend whose story deserves keeping). The operator's agent preps each session; the operator conducts it. Hard rule for this mode: the repo must be transferable to the subject at any moment, so only their story goes in. See `AGENTS.md`.

Either way, capture streams can be hybrid: prepared interview sessions are the spine; self-serve chat captures, voice memos, and mailed-in chapters are tributaries that get processed identically.

## Getting started

Follow [`GENERATE.md`](./GENERATE.md). Short version: fork private, fill `SUBJECT.md`, intake whatever already exists (journals, manuscripts, old interviews) into `sources/`, let the agent process the seed, and run your first prepared session. Files and folders prefixed `_example-` show the conventions; delete them once real content exists.
