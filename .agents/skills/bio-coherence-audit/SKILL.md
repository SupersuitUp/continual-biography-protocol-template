---
name: bio-coherence-audit
description: Run the periodic Compound-phase audit over the biography corpus. Finds thin eras, unprocessed captures, stale contradictions, aging media asks, and STATE.md bloat, then feeds the findings into the next session guide. Use every 5 to 10 captures, monthly, or when the biographer says "audit the corpus" or "how healthy is the biography".
---

# Coherence Audit

Phase 4 of the loop in [`AGENTS.md`](../../../AGENTS.md). The audit's output is interview fuel, so it ends by updating `STATE.md`, never as a report that goes nowhere.

## Checks

1. **Era density.** Compare event counts per era in `chronology.md` against `SUBJECT.md` priorities. Name the thinnest priority eras.
2. **Processing debt.** Grep `captures/` for `processed: false`. Any hit is debt; list them.
3. **Stale contradictions.** Contradictions in `STATE.md` older than three sessions get flagged for the next guide.
4. **Aging media asks.** Asks pending longer than a month either escalate into the next session guide or get retired with a reason.
5. **Link integrity.** Spot-check that chronology events, people facts, and quotes resolve to real capture/source files.
6. **STATE.md size.** If it no longer fits on roughly one screen, archive resolved material into the relevant layer files.
7. **Orphan people and themes.** Person files never linked from chronology, theme files stuck below three evidence bullets: candidates to merge, grow, or retire.

## Output

- Fix what is mechanical (links, archiving, retired asks) in place.
- Write what needs the subject (thin eras, stale contradictions, escalated asks) into `STATE.md` → Open threads and Next Session.
- One-paragraph summary to the biographer: corpus health, debt, and the single highest-leverage next session.
