# Gate Proof R10 handoff

## Objective

Bootstrap Gate Proof R10 as a greenfield Praxis pilot.

## Current state

- Praxis 3.12.0 greenfield profile installed on 2026-11-06; Praxis 3.25.0 since
  WI-0002 (2026-11-25).
- Conditor-governed since WI-0002 (2026-11-25): the owner authorized
  `conditor init` (Conditor 0.10.29), which added the Conditor lock, the
  `fsharp-limen-web` scaffold, the Indy-init requirements and the ready mission
  COND-MISSION-001. `conditor upgrade --current` then moved the repository to
  echelon-current 1.42.0: Praxis 3.25.0, Ordo 1.20.0, Aegis 2.0.2, Forma 1.0.1
  (scaffold page migrated with Forma's NamespaceMigrator; Folio's `ef-print-*`
  elements are Folio's own names and stay), Limen 0.9.1, Folio 0.4.1, Percepta
  0.1.0, and the optional Echelon theme 1.1.0 (loaded after Forma `all.css`:
  `echelon.css`, `echelon-fonts.css`, `echelon-app.css`).
- Upstream sync is configured against `origin/main`, whose history is unrelated
  to the default branch `proof`, so `praxis sync check` reports `unavailable`.
- Project charter is a draft.
- No first vertical slice, evidence record, hypothesis, or experiment has been
  accepted.
- The operating system is under evaluation.

## Validation

Run:

```bash
./praxis registry check
./praxis validate
```

## Continuity

An executor session is disposable. Before handing off, commit and push the
work, record `./praxis work checkpoint --id ID --occurred-at NOW --summary ...
--next-action ...`, and push the `.ros/` state. A successor reads
`./praxis work context ID --text` and takes over with `./praxis work continue`.

## Unresolved questions

1. What concrete communication problem and user should the first slice serve?
2. What baseline workflow will be used for comparison?
3. What data, privacy, safety, and accessibility constraints apply?
4. Which outcome would distinguish useful engineering from additional process?

## Next action

Complete `PROJECT-CHARTER.md`, choose the first bounded outcome, and record its
baseline and acceptance criteria in `context/CURRENT-STATE.md`.
