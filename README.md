# DeFi Incident Tracker — Dataset

A continuously-updated, machine-readable, **source-linked** record of DeFi
security incidents: exploits, protocol responses, and loss estimates where the
source stated one.

> **Published by [DeFi Safety Tools](https://defisafetytools.com/incidents/).**
> Every record carries at least one primary source URL.

## Files

| File | Format | Notes |
|---|---|---|
| `incidents.json` | JSON | Full dataset, incl. per-record `qualityFlags` (honest markers of data quality — see below) |
| `incidents.csv` | CSV | Same records, one per line, RFC 4180 escaped |

## Current snapshot

- **1,386 records**
- Coverage window: **2026-09-10 to 2026-11-13** — a short window, *not* a historical archive
- Status: **226 confirmed** / **1,160 under review**
- Loss figures are estimates **as reported by the original source**, not independently audited

## Field schema

| Field | Meaning |
|---|---|
| `id` | Stable record id |
| `protocol` | Affected protocol (some rows carry a source-fed headline — flagged, not removed) |
| `chain` | Blockchain (blank / "Not specified" when the source did not state one) |
| `technique` | Attack technique where known |
| `lossUsd` | Loss estimate in USD, or `null` when unsourced |
| `status` | `confirmed` / `review` / `resolved` |
| `severity` | Editor-assessed severity |
| `confidence` | `0..1` — reviewer confidence in the record's *sourcing*, not in the loss figure |
| `firstSeen` | Date the event was first observed |
| `updatedAt` | Last update |
| `summary` | Short summary |
| `sourceUrls` | Primary source links (at least one per record) |
| `qualityFlags` | Objective quality markers (e.g. `loss-unknown`, `chain-unspecified`) |

## License

**CC BY 4.0** — reuse freely with attribution and a link back to the tracker.
See [LICENSE](LICENSE).

## Permanently archived

Every snapshot is also archived with a DOI on **Zenodo** (operated by CERN).
The concept DOI always resolves to the latest version:

**[10.5281/zenodo.23209336](https://doi.org/10.5281/zenodo.23209336)**

## How it updates

Records are appended as the tracker runs. The live tracker at
[defisafetytools.com/incidents/](https://defisafetytools.com/incidents/)
is always at or ahead of this copy; earlier snapshots remain available under
the same concept DOI.

---

*This is a derived work: underlying facts come from the linked third-party
sources; the compilation, cleaning, and quality flagging are ours. If a source
disputes a record, the tracker carries a correction with its own source link.*
