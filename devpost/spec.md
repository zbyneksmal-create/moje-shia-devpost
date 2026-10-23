---
doc: spec
status: draft
created: 2026-10-23
provenance: new reconstruction document, not recovered original
---
# Moje Shia — Technical Specification

## How This Works, In Plain Language
The page holds four area switches and a fixed list of eight movements. The chosen area names become part of a web link. The QR encodes that same link. Opening it displays the corresponding client plan. Nothing needs to be saved in a client database.

## The Core Journey Through the System
Implements `prd.md > The Core Journey`: selection changes an in-memory Set; `matches()` reads the fixed movement map; `clientUrl()` serializes allowlisted group keys; `renderHandover()` generates QR locally; `renderClient()` reads and validates URL parameters before displaying the same map.

## Stack
New readable HTML, CSS and plain JavaScript, using standard browser APIs. No build or dependency installation. This is an implementation simplification for reconstruction, not a claim that the original hosted bundle used this stack.
QRCode.js is a bundled standard MIT dependency: https://github.com/davidshimjs/qrcodejs. The exact downloaded file's fingerprint is recorded in `PROVENANCE.md` after packaging. Node.js 18+ serves local preview using the standard HTTP module: https://nodejs.org/api/http.html.

## Where It Runs and How Someone Tries It
Run `node server.cjs` from the repository root; open http://127.0.0.1:8980. The server binds only to loopback and serves an explicit runtime-file allowlist. No API keys, environment secrets or database bindings.
For another device to scan a QR, use an explicitly authorized reachable HTTPS deployment of these same static files. A loopback QR is not claimed to work on a separate phone.
Devpost still requires a public repository and publicly viewable short YouTube/Vimeo demonstration; hosting alone is insufficient.

## Look and Feel
Implements `prd.md > Look and Feel`: CSS variables define dark greens, light text and green accents; system fonts for body and Georgia for the italic line. Two columns collapse below 680px. No external fonts or image fetches.

## Components
### Movement catalogue
`app.js`: `AREAS`, `MOVEMENTS`, `DISCLAIMER`, copied as text from the competition reference. Implements `prd.md > Matched movements`.
### Therapist flow
`renderTherapist()`, `choose()` and `bodyMap()` implement area selection, accessible controls and preview.
### Sharing
`clientUrl()`, `renderHandover()`, QRCode.js and clipboard fallback implement client handover.
### Client route
`validAreas()` rejects unknown keys; `renderClient()` displays allowlisted movement data only. Implements client reading and invalid-query state.
### Local preview
`server.cjs` serves four runtime assets plus index.html; all other routes return 404. It does not expose repository metadata or local documents.

## Data Model
`selected`: in-memory Set of four possible strings. `MOVEMENTS`: immutable-in-practice source catalogue. URL query: `view=client&areas=neck,trapezius,shoulders,forearms` (subset allowed). Unknown and duplicate group keys are discarded. No persistent storage or requests containing client information.

## File Structure
| File | Purpose |
| --- | --- |
| index.html | Entry point |
| app.js | Catalogue, selection, routing and handover |
| style.css | Responsive reference-aligned presentation |
| qrcode.min.js | Bundled standard QR library |
| server.cjs | Loopback-only preview |
| LICENSE / THIRD-PARTY-LICENSES.txt | Project and dependency licensing |
| devpost/*.md | Planning, provenance, verification, demo preparation |
| devpost/app-map.html | Readable guide to the implemented flow |

## External Services and Dependencies
No runtime external API, analytics, AI service, client database or CDN. QRCode.js executes locally; hosting serves static files only. The public source repository and video service are submission distribution, not application dependencies.

## Important Failure Modes
- Unknown or tampered area query: discard unknown values, do not interpolate them into HTML.
- Clipboard unavailable: expose a read-only selected URL for manual copying.
- QR generation unavailable: keep direct link usable.

## What Was Simplified and Why
The missing original framework source is replaced with a small standalone implementation of the observed flow. It is disclosed as newly written reconstruction, with no production code reuse. No backend is needed to demonstrate this particular stateless handover.

## Decisions and Open Issues
The owner authorized creating missing sources and submission materials, preserving existing competition behavior and protected production systems. Routine implementation choices are the agent's, not falsely attributed to the owner.
The practical uncertainty was whether the original source could be retrieved. Repository host DNS failed; reconstruction was therefore authorized. Remaining issues: final owner review, public distribution and demo upload.
