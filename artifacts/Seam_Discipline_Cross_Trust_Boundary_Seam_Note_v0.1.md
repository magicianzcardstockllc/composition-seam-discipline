# Cross-Trust-Boundary Seam Note v0.1
## Seam Discipline — Reviewer Guidance for Ungoverned Adjacent Layers

**Authority:** James Aull / MagicianzCardstock LLC
**Date:** June 2026
**Status:** Canonical v0.1

---

## Non-Causal Statement

This document is categorically non-causal. It does not authorize intervention, halt, escalation, or remediation. It defines reviewer-side documentation and inference limits when a composed governance path includes a layer that cannot produce independently reviewable governed-state evidence. It preserves the question; it does not answer it.

---

## Purpose

The Seam Discipline's Correlation Contract assumes that both layers in a composed path have declared boundaries and can emit the minimum stitching surface: `decision_correlation_id`, `event_window`, `scope_hash`, and `artifact_hash`.

In practice, this assumption frequently fails.

AI systems increasingly operate alongside legacy systems, proprietary infrastructure, inherited authority surfaces, and operational technology that predates modern governance frameworks. These adjacent systems carry real authority and real consequence — but they have no mechanism to emit independently reviewable governed-state evidence at the boundary.

When a governed AI layer sits beside an ungoverned adjacent layer, the reviewer faces a composed path where one side can be examined and the other cannot. The Cross-Trust-Boundary Seam Note defines how a reviewer documents, bounds, and draws inference-safe conclusions from that asymmetry.

---

## Controlling Invariant

A clean ASRO record on one side of a composed path does not certify the governed state of an ungoverned layer on the other side.

The absence of evidence from an adjacent layer is not evidence of absence. It is a gap that must be named, not resolved.

---

## Document Non-Claims

This note does not:
- Define a standard for legacy system governance or remediation
- Certify that a composed path is compliant, safe, or admissible because the governed side has a clean record
- Determine whether the ungoverned adjacent layer was operating appropriately
- Assign responsibility for the absence of governed-state evidence from the adjacent layer
- Authorize continuation, execution, or consequence based on the governed layer's record alone
- Replace external review, legal review, or institutional accountability for the ungoverned layer

---

## Definitions

**Governed layer:** A layer that has declared its boundary, emits the minimum stitching surface, and produces independently reviewable governed-state evidence at the consequential boundary.

**Ungoverned adjacent layer:** A layer that carries authority or consequence at the same boundary but cannot produce independently reviewable governed-state evidence. This includes but is not limited to: legacy systems, proprietary infrastructure, inherited operational technology, systems without declared non-claims, and systems that produce only self-reported logs.

**Cross-trust-boundary seam:** The consequential boundary where a governed layer and an ungoverned adjacent layer interact such that the output of one affects the consequence of the other.

**Opacity gap:** The evidentiary gap created when one side of a composed path cannot emit independently reviewable evidence. The opacity gap must be named, not treated as a neutral condition.

---

## The Three Failure Modes This Note Addresses

**Failure Mode 1 — Clean record on one side treated as joint certification:**
A reviewer examines a complete, hash-verified ASRO record and infers that the entire composed path — including the ungoverned adjacent layer — was properly governed. The ASRO record certifies nothing about the adjacent layer. This is the most common and most dangerous inference error.

**Failure Mode 2 — Absence of adjacent evidence treated as neutral:**
A reviewer notes that no evidence exists from the adjacent layer and treats this as a non-event. Absence of evidence from a layer carrying authority and consequence is not neutral — it is a named gap that must appear in the Review Bundle Map and may require a Divergence Event Record.

**Failure Mode 3 — Ungoverned layer's authority inherited by the governed layer:**
A reviewer treats the governed layer's corroboration of an ungoverned layer's output as evidence that the ungoverned layer's authority was valid. A governed layer can record that it received input from an adjacent system. It cannot certify that the adjacent system's authority posture, policy state, or decision conditions were appropriate.

---

## Reviewer Protocol

### Step 1 — Identify the cross-trust-boundary seam

Before applying the Correlation Contract, determine whether all participating layers in the composed path can emit the minimum stitching surface.

If any adjacent layer cannot emit `decision_correlation_id`, `event_window`, `scope_hash`, and `artifact_hash`, the seam is a cross-trust-boundary seam and this note applies.

### Step 2 — Name the opacity gap explicitly

The opacity gap must appear in the Review Bundle Map Section 3 (Absent Artifacts) as a named gap, not a silent absence.

Required fields for naming the opacity gap:

```json
{
  "absent_layer_ref": "descriptive identifier for the ungoverned adjacent layer",
  "opacity_type": "legacy_system | proprietary_infrastructure | inherited_authority | operational_technology | undeclared_boundary | other",
  "consequence_relationship": "description of how the ungoverned layer's output or authority affected the governed layer's consequential boundary",
  "evidence_available": "none | partial_self_reported | partial_third_party | other",
  "opacity_gap_note": "The absence of independently reviewable governed-state evidence from this adjacent layer is a named gap, not a neutral condition. It does not indicate that the adjacent layer was operating appropriately or inappropriately. It indicates that independent review of its governed state at this boundary is not currently possible."
}
```

### Step 3 — Bound inference from the governed layer's record

Every inference drawn from the governed layer's record must be explicitly bounded at the cross-trust-boundary seam.

The reviewer must record which conclusions are supported by the governed layer's evidence and which conclusions require evidence from the ungoverned adjacent layer that is not available.

Permitted inferences from a governed layer's record:
- What the governed layer declared its authority posture to be
- What the governed layer recorded about inputs it received from the adjacent layer
- What the governed layer's policy state and tool access were at the boundary
- What divergence the governed layer detected between its declared conditions and observed conditions

Prohibited inferences from a governed layer's record alone:
- That the adjacent layer's authority was valid or appropriate
- That the adjacent layer's output was produced under governed conditions
- That the composed path as a whole was compliant, authorized, or safe
- That the absence of detected divergence on the governed side means no divergence existed on the adjacent side

### Step 4 — Emit a Divergence Event Record for the opacity gap

When a cross-trust-boundary seam is identified, emit a Divergence Event Record using the following divergence nature codes:

**New divergence nature codes for cross-trust-boundary seams:**

`ADJACENT_LAYER_UNGOVERNED` — The adjacent layer at this consequential boundary has not produced independently reviewable governed-state evidence. The governed layer's record cannot substitute for it.

`OPACITY_GAP_UNDOCUMENTED` — A cross-trust-boundary seam was identified but the opacity gap was not named in the Review Bundle Map. This code is emitted when a reviewer detects a prior failure to name the gap.

`GOVERNED_RECORD_OVERCLAIMED` — A governed layer's record has been cited or used in a way that implies it certifies the governed state of an adjacent ungoverned layer.

`INHERITED_AUTHORITY_UNVERIFIABLE` — The governed layer's record shows that it received input from or deferred to an adjacent layer whose authority posture, policy state, and decision conditions cannot be independently reviewed.

### Step 5 — State the residual review limitation

Every composed-path review involving a cross-trust-boundary seam must carry the following standing limitation in the Review Bundle Map:

> *This composed path includes at least one adjacent layer that cannot produce independently reviewable governed-state evidence at this boundary. The governed layer's record has been reviewed and verified. The ungoverned adjacent layer's governed state at this boundary cannot be independently reviewed. Conclusions drawn from this review are bounded by this limitation. The clean record on the governed side does not extend to the ungoverned side.*

---

## Legacy Systems — Specific Guidance

Legacy systems are the most common source of cross-trust-boundary seams in enterprise, clinical, infrastructure, and industrial deployments.

A legacy system at a consequential boundary typically exhibits one or more of the following:
- Self-reported logs only — no independently retrievable governed-state evidence
- No declared authority posture, policy state, or non-claims
- No mechanism to emit `decision_correlation_id` or `scope_hash`
- Authority established before modern governance frameworks and never formally declared
- Decision conditions that cannot be reconstructed from available records

When ASRO sits beside a legacy system at a consequential boundary, the governed-state record ASRO produces covers the AI system's side of the boundary. It does not extend to the legacy system's side.

Reviewers must treat the legacy system's side as an opacity gap and name it explicitly. The clean ASRO record is not a substitute for the legacy system's undeclared governed state.

---

## Operational Technology and Critical Infrastructure

In critical operational environments — including industrial control systems, clinical decision support, infrastructure management, and safety-critical workflows — the cross-trust-boundary seam carries the highest evidentiary stakes.

When an AI system and an operational technology system interact at a consequential boundary:

- The AI system's governed-state record covers the AI side
- The operational technology's authority posture, policy state, safety conditions, and decision parameters may not be independently reviewable
- Divergence between the two systems may not be detectable from either side's record alone
- A clean AI governance record does not certify that the operational technology was operating within its declared safety parameters

The opacity gap in these environments is not a minor documentation issue. It is the evidentiary gap where accountability becomes most fragile and where independent review is most needed and least available.

This note does not close that gap. It names it so that reviewers, auditors, and accountability authorities can see it rather than inheriting a false sense of completeness from the governed side's clean record.

---

## Relationship to Other Seam Discipline Artifacts

| Artifact | Relationship |
|---|---|
| Correlation Contract v0.1 | This note applies when the Correlation Contract's minimum emission standard cannot be met by all participating layers. |
| Divergence Event Record v0.5.1 | Four new divergence nature codes are added: `ADJACENT_LAYER_UNGOVERNED`, `OPACITY_GAP_UNDOCUMENTED`, `GOVERNED_RECORD_OVERCLAIMED`, and `INHERITED_AUTHORITY_UNVERIFIABLE`. |
| Review Bundle Map v0.1 | Section 3 (Absent Artifacts) must name the opacity gap using the fields defined in Step 2 of the reviewer protocol above. |
| Declaration Intake Profile v0.2 | An ungoverned adjacent layer has no companion profile and cannot complete the intake. Its absence from a completed declaration or companion profile may be relevant to the Review Bundle Map when that layer participates in a consequential boundary. |
| Layer Non-Claims Matrix v0.1 | An ungoverned adjacent layer has no declared non-claims. Reviewers must not infer non-claims for a layer that has not declared them. |

---

## Living Governance Stack Map — Legacy Systems as a Candidate Layer Position

The cross-trust-boundary seam problem suggests a candidate addition to the Living Governance Stack Map between Layer 9 (Institutional Deployment) and the general stack:

**Candidate: Governed-State Opacity at Inherited Authority Boundaries**

The unsolved question: what governed state existed at the boundary between a modern AI governance layer and an inherited authority system that predates independent reviewability as a design requirement?

The remaining gap: no current layer owns the evidentiary problem of systems carrying real authority and real consequence that cannot produce independently reviewable governed-state evidence. The governed layer records what it declared and what it received. The ungoverned adjacent layer's conditions remain unwitnessed.

This is not a Layer 9 institutional deployment problem — it is a structural evidentiary gap that exists regardless of how well the governed layer performs.

---

*Seam Discipline — Cross-Trust-Boundary Seam Note v0.1*
*ASRO™ is a trademark of MagicianzCardstock LLC. Serial No. 99827630.*
