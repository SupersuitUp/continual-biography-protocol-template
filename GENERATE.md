# GENERATE.md: bootstrapping a CBP instance

The canonical procedure for standing up a new Continual Biography Protocol workspace. An agent handed this file plus an empty fork should be able to reach "first prepared session" without further instructions.

## Phase 0: Fork

```bash
gh repo create <owner>/<subject>-biography \
  --template SupersuitUp/continual-biography-protocol-template \
  --private --clone
```

**Private is mandatory.** The repo will hold raw testimony.

## Phase A: Configure the subject

Interview whoever is commissioning the biography (the subject themselves, or the biographer acting for them) and fill [`SUBJECT.md`](./SUBJECT.md). One question at a time:

1. Who is this biography about? (Name, birth year if shareable, one-line identity.)
2. Who is it ultimately for, and what should it do for them?
3. Which parts of the life matter most to get right?
4. What is off limits, and what must be preserved verbatim?
5. Which named third parties need careful handling?
6. Which projections are already wanted? (Memoir, narrated site, film, children's book, art series, family wiki.) Create a stub brief in `projections/` for each.
7. Who runs it: self-run or biographer-run? If biographer-run, confirm the transferability rule in `AGENTS.md` is understood.

## Phase B: Seed intake

Gather everything that already exists and file it into `sources/`:

- Manuscripts, journals (scanned or photographed), letters, clippings.
- Prior interviews or chat-app capture sessions (per [The Capture-First Autobiography](https://appliedai.wiki/playbooks/capture-first-autobiography) quick-start; those transcripts move into `captures/` with `mode: self-capture`).
- Existing photos and video into `media/` with rows in `media/INDEX.md`.
- Biographer-run mode: any notes or transcripts the biographer already holds about the subject, **sanitized first**. Only the subject's story goes in; strip anything third parties shared in confidence and anything the biographer would not hand the subject tomorrow.

Then run the Process phase from `AGENTS.md` over each seed source, largest first. This births the initial `chronology.md` era map, the first `people/` and `themes/` files, and the first entries in `quotes.md`.

**At large seed scale (hundreds of pages, dozens of sessions), fan out.** Dispatch one extraction agent per source batch (e.g. 50 manuscript chapters, or 4-6 session transcripts each), all with the same output schema: EVENTS / PEOPLE / THEMES / QUOTES (verbatim) / PROJECTION BEATS / OPEN THREADS / DATE CONFLICTS, every line source-tagged. File each agent's extraction verbatim into `sources/` (for biographer-held transcripts, the sanitized extract IS the in-repo source document; the raw recording stays in the biographer's archive), then merge into the layers yourself. A source-tag legend file in `sources/` keeps chronology rows compact. Proven at ~1.1M characters of seed in one pass.

## Phase C: First STATE.md

Write `STATE.md` from the seed: the era map with density judgments (which eras are thin), open threads the sources raised but never answered, contradictions between sources, media asks, and the intake queue of anything not yet processed. Finish with the first **Next Session** guide.

## Phase D: First session

Run the loop from `AGENTS.md`: prep is already done (Phase C), so capture, process, compound. Delete the `_example-` files once real content exists.

## Hard-won rules

- **Do not skip Phase B to "get to the interviews."** A seeded instance asks question forty on day one; an unseeded one wastes three sessions rediscovering what a manuscript already said.
- **Do not summarize sources instead of processing them.** A summary is not an event list. Every event extracted must carry its source link.
- **Keep the first session guide humble.** One era, a handful of threads. The subject's tangents are usually better than the script; the guide exists so tangents have somewhere to land.
