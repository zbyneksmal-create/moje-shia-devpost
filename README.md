# Moje Shia — Movement Aftercare

A standalone competition proof of concept: select treated body areas, review matching home movements, and hand the same plan to a client with a QR code or link.

## Run locally

Requires Node.js 18 or later. No package installation, API key, database, or account is needed.

```sh
node server.cjs
```

Open http://127.0.0.1:8980. Select one or more areas, press **Create client plan**, then **Open client view**. A local QR link works only on the same computer; to scan it on another device, serve these static files on a reachable HTTPS origin. Local preview intentionally binds to loopback only.

## What is included

- Four area groups: neck, trapezius, shoulders, forearms.
- Two existing movement descriptions per group, with repetition guidance and stop conditions.
- Keyboard-operable body map and labelled area buttons.
- Therapist preview, handover screen, client view, locally generated QR, and copy-link fallback.
- Share URLs contain only allowlisted area identifiers. No client names, visits, medical records, recordings, or production integrations.
- General aftercare, not AI diagnosis or personalized clinical treatment. The matching is deterministic; AI assisted development, not runtime diagnosis.

## Source provenance

The owner's separate competition prototype existed on 8 October 2026. On 23 October its hosted UI was inspected, but its original source repository could not be retrieved. **This repository is a newly written, readable reconstruction of that competition flow, not a recovered copy of the original source.** Movement wording and the four-area interaction were transcribed from that prototype. No production Moje Shia code or real client data was used.

The earlier hosted reference is https://moje-shia-devpost.zbynek-smal.chatgpt.site/ (owner-private at inspection). This repository is not automatically synchronized with that deployment. Until explicitly updated, the hosted reference and this reconstruction are different builds of the same competition concept. Review and record this repository's local build for an accurate submission.

## Planning and Devpost Learn

`devpost/scope.md`, `devpost/prd.md`, `devpost/spec.md`, and `devpost/checklist.md` document this reconstruction using the official [Devpost Learn Skill Pack](https://github.com/challengepost/learn-ai-basics). They were created on 23 October and are **not backdated originals**. Final owner review is recorded separately; unchecked items are not claimed complete.

See `devpost/PROVENANCE.md` for the development process and `devpost/app-map.html` for code navigation. The owner's personal learner profile is ignored and must not be published.

## Verification

```sh
node --check app.js
node --check server.cjs
```

Browser verification results and outstanding checks are recorded in `devpost/checklist.md`.

## Demo

`devpost/demo-script.md` specifies the actual interaction to record. A finished video must show this build working, including selection, QR handover, and the client view; a slide deck alone is insufficient. The public YouTube/Vimeo URL must be added to Devpost before submission.

## License

Project code: MIT, see `LICENSE`. QRCode.js is a standard third-party library by davidshimjs under MIT, included in `qrcode.min.js`; its notice is retained in `THIRD-PARTY-LICENSES.txt`. See https://github.com/davidshimjs/qrcodejs.
