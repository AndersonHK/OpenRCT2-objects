# Objects fork migration

Owner direction: use this fork as the authoritative object source; preserve its data-owned gameplay/audio choices.

Baseline: `cc4a8cb02308218f3b1388882af5fe068df218d8`. Frozen upstream target: `046ae328114fe347bee6f9f90561cd8bc24ce787`.

Four source commits are recorded individually in parent order. No push/release performed. Four existing kart definitions retain `frictionSoundGainDb: -6.0`.

Before migration, 419 untracked packed release artifacts were verified against objects v1.7.11 (418 exact; one temporary kart calibration), backed up in the engine workspace at `obj/upstream-audit/objects-output-artifacts-backup.zip`, then removed from the source tree. Three formatting-only changes from the temporary workaround were restored to HEAD. The rejected workaround was never committed.


## O001 — Fix Bengal tiger description typo

- Source: `b429d74251264728470119fc119b32f02255aa7c`. Remaining: 4 → 3.
- Decision: Text only; keep vehicle behavior and fork kart gains.
- Validation: inspected source delta; JSON parsing, all four kart gains, exact-one ancestry and whitespace checks passed. Exporter build remains pending until O004.
- Receipt: unique `Upstream-Commit: b429d74251264728470119fc119b32f02255aa7c` trailer in first-parent history.

## O002 — Add Catalan spinning-car translations

- Source: `a47f48275c54202c512f2222a23cfcb3644dde22`. Remaining: 3 → 2.
- Decision: Adopt Catalan labels; omit accidental reintroduction of themend in the English tiger description.
- Validation: inspected source delta; JSON parsing, all four kart gains, exact-one ancestry and whitespace checks passed. Exporter build remains pending until O004.
- Receipt: unique `Upstream-Commit: a47f48275c54202c512f2222a23cfcb3644dde22` trailer in first-parent history.

## O003 — Record English typo correction already preserved

- Source: `cfdbe55f83f703484ed467246db98bff30b3c9ca`. Remaining: 2 → 1.
- Decision: No product change: O002 deliberately retained the corrected English spelling.
- Validation: inspected source delta; JSON parsing, all four kart gains, exact-one ancestry and whitespace checks passed. Exporter build remains pending until O004.
- Receipt: unique `Upstream-Commit: cfdbe55f83f703484ed467246db98bff30b3c9ca` trailer in first-parent history.

## O004 — Update object exporter ImageSharp API and package

- Source: `046ae328114fe347bee6f9f90561cd8bc24ce787`. Remaining: 1 → 0.
- Decision: Use source actual version 2.1.13, not stale subject 2.1.10; preserve pixel loop coordinates and indexed colors.
- Validation: inspected source delta; JSON parsing, all four kart gains, exact-one ancestry and whitespace checks passed. Exporter build remains pending until O004.
- Receipt: unique `Upstream-Commit: 046ae328114fe347bee6f9f90561cd8bc24ce787` trailer in first-parent history.
