---
name: bio-prep-session
description: Prepare the next biography interview session. Reads SUBJECT.md, STATE.md, and the chronology, then rewrites STATE.md's Next Session section into a concrete interview guide (focus era, open threads as questions, contradiction checks, media asks). Use when the biographer says "prep the next session", "what should I ask next", or before any scheduled interview.
---

# Prep Session

Phase 1 of the loop in [`AGENTS.md`](../../../AGENTS.md). The output is a rewritten **Next Session** section in `STATE.md`, nothing else.

## Steps

1. Read `SUBJECT.md` (priorities and ground rules bind everything below).
2. Read `STATE.md` in full: open threads, gaps by era, live contradictions, pending media asks, intake queue.
3. Skim `chronology.md` for era density; note the thinnest era touching the subject's priorities.
4. If the intake queue is non-empty, flag it at the top of the guide: unprocessed material may already answer open threads, so consider running `bio-intake-source` before interviewing.
5. Rewrite `STATE.md` → **Next Session**:
   - One focus (the thinnest priority era, or the hottest open thread).
   - 3 to 5 open threads phrased as the questions a curious biographer would ask, each citing the capture that raised it.
   - Contradiction checks phrased gently: present both versions, let the subject reconcile.
   - Media asks to make in person, pulled from Pending media asks.
6. Update the *Last updated* line.

## Rules

- Keep the guide humble: one era, a handful of threads. Tangents beat scripts; the guide exists so tangents have somewhere to land.
- Never put an off-limits topic (per `SUBJECT.md`) in the guide.
- One question at a time in the session itself; the guide is a quiver, never a questionnaire.
