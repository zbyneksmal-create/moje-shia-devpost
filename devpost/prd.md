---
doc: prd
status: draft
created: 2026-10-23
provenance: new reconstruction document, not recovered original
---
# Moje Shia — Product Requirements

Source: `scope.md > The Core Loop` and `The POC Boundary`.

## The Core Journey
1. Therapist opens the app and sees no preselected areas.
2. Therapist selects one or more of four area groups on the figure or labelled buttons.
3. Matching movements update immediately; no names or free-text health notes are entered.
4. Therapist reviews the list and creates the client plan.
5. Handover shows a QR and an ordinary client link representing the same selections.
6. Client opens the link and reads instructions, repetition guidance and stop conditions.

## Screens and Layout
Therapist selection with body map and movement preview; handover with movement list and QR panel; mobile client reading surface. No additional user screen.

## Look and Feel
Retain the competition reference's dark green, pale text, green accents and serif italic secondary headline. Cards and labels remain readable on a narrow phone. Keyboard controls have visible focus. No new marketing content.

## Features and Behavior
### Area selection
Four independent toggles: neck, trapezius, shoulders, forearms. Left/right shapes for shoulders and forearms toggle their shared group. Selected state is visible and exposed as `aria-pressed`.
Acceptance: selecting then deselecting Neck returns to the empty preview; choosing both shoulder shapes cannot create duplicate shoulder plans.

### Matched movements
Exactly two existing movements per group. Keep original wording, repetition guidance and stop conditions. This is a fixed lookup, not a medical recommendation model.
Acceptance: all four groups produce eight unique movements; an unknown URL parameter produces no invented exercise.

### Client handover
Create is available only with at least one selected group. Handover offers a locally generated QR, direct client link, and Copy link. Clipboard failure exposes a selectable URL.
Acceptance: the decoded QR, direct link and copied text describe the same allowlisted groups. No name, note, ID or token is appended.

### Client reading
Show only the groups encoded in the URL, their movement instructions and the existing general-aftercare notice. No login or storage is required in this reconstructed static build.

## States and Boundaries
- Empty selection: instructions to choose an area, no active create action.
- Invalid client query: clear empty-plan text and safety notice, no raw query echoed.
- QR failure: client link remains available.
- Clipboard denied: selectable link fallback.
- Leaving/reloading therapist view resets selection; client URL retains its encoded groups.

## Product Decisions
The owner chose to complete one standalone English competition application and preserve production systems. The four-area behavior and existing exercise content are carried forward from the inspected prototype, rather than claimed as new owner preferences.

## What We're Building
Only the core journey above and the submission materials needed to explain and reproduce it.

## Deferred From the POC / Non-Goals
No client database, appointment workflow, medical diagnosis, runtime model, payments, accounts or production integration.

## Open Questions
Final owner review, public repository URL, video upload URL, and the owner's subjective Devpost survey answers remain pending. No unanswered question is silently filled with a fabricated answer.
