# Converge Workspace

This directory is the project-local Converge control plane. Product code stays
in the repository's normal application directories; the artifacts here record
why work exists, what was authorized, how it ran, and what proved it complete.

## Lifecycle

`brain → docs → swimlanes → tasks → execution → receipts`

| Path | Contract | On this tree |
|---|---|---|
| `brain/` | Raw inputs and append-only discovery material | Empty scaffold (`.gitkeep`). The week's brain is `brain/notebooklm/` at the repo root |
| `docs/` | Reviewed product and technical decisions | Empty scaffold. The papers live in the repo-root `docs/` (BRD, tech-spec, ADRs `0001`–`0015`, seams, three Consensus signs) |
| `swimlanes/` | Decomposition, lanes, and consensus evidence | Three lanes: `ingest-landing/`, `dlt-gold/`, `orchestrate-serve/` |
| `tasks/` | Task-Specs and their lifecycle projection | 16 HMAC-signed copies (`signed_off_sig`) of the Nights 2–4 leaves, each `accepted: true` since 2026-09-10. The authored Task-Specs are `docs/tasks/` (18, including the two Type `06` leaves that were never copied here); their frontmatter was not updated with the signatures or the acceptance |
| `execution/` | Runtime contracts bound to signed Task-Spec hashes | 15 folders — every signed leaf except `T-20260825-type-01-landing-parser` |
| `receipts/` | Write-once settlement evidence | No tracked receipts; the week's packets went to the gitignored `evidence/` |
| `.taskspec/acceptance/` | Owner acceptance records | 16 records, 2026-09-10 — Types `01`–`05` accepted **Tier 2, owner-supervised**. This is the completion record: loop settlement into `tasks/done/` fails `HANDOFF_STALE` on this repo |

There is no tracked `sketch/` or `loop/` directory; `cvg init` (Night 4, 2026-08-27)
did not create them. Local loop attempts write to the gitignored `loop/`.

Task-Spec frontmatter is canonical. `tasks/_state.yaml` is a derived,
rebuildable projection — the copies here and in `docs/tasks/` were last
regenerated on 2026-08-28 and do not reflect what Nights 4–5 built or the
2026-09-10 acceptance; every leaf still reads `ready`. Rebuild before trusting them. External trackers are optional projections, never the
authoring source.
