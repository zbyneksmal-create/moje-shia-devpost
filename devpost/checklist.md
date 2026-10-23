---
doc: checklist
status: draft
---
# Build Checklist

Build mode: fast, as explicitly requested by the owner. Final review remains required.

## Slices
- [ ] **1. Area selection produces the existing movement preview**
  Becomes usable: Open a standalone therapist page and match selected areas to two existing movements each.
  Why now: Proves the central lookup without production access.
  PRD ref: `prd.md > Area selection`, `Matched movements`
  Spec ref: `spec.md > Movement catalogue`, `Therapist flow`
  Build: New static source, exact existing content, accessible controls.
  Verify (mechanical): Syntax check; browser empty, single, all-area and deselection checks.
  Learner check: Confirm the reference flow is represented without added scope.
  Commit: `Reconstruct competition selection and movement preview`
- [ ] **2. The same plan opens through a QR/link**
  Becomes usable: Therapist handover and client view share the same allowlisted plan.
  Why now: Completes the distinctive end-to-end flow.
  PRD ref: `prd.md > Client handover`, `Client reading`
  Spec ref: `spec.md > Sharing`, `Client route`
  Build: Local QR library, copy fallback, query validation, client safety text.
  Verify (mechanical): QR/link equivalence, invalid URL, mobile overflow, clipboard behavior.
  Learner check: Open the delivered client plan and confirm the handover.
  Commit: `Complete isolated client handover and submission documentation`

## Hands-on Checkpoints
- [ ] Final owner exploration and feedback on this reconstruction

## Final Review
- [ ] Owner confirms the reconstructed result and planning documents are ready
- [ ] Public repository and license links verified
- [ ] Public demo video URL verified and added to Devpost
- [ ] Owner supplies subjective survey answers
- [ ] Owner approves final submission

## Code Tour and App Map
- [ ] `app-map.html` checked and shown with the working result
Reference route: `choose()` → `matches()` → `clientUrl()` → `renderClient()`. No claim of a completed personal learning activity is made.

## Revisions
- Original hosted source unavailable: newly written reconstruction is explicitly disclosed. Existing production code and records excluded.
