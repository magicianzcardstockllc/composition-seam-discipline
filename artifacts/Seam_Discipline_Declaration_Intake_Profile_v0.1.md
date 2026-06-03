# Seam Discipline — Declaration Intake Profile v0.2
## Reviewer-Side Intake Rubric for Independently Authored Governance Artifacts

**Authority:** James Aull / MagicianzCardstock LLC
**Date:** June 3, 2026
**Status:** Canonical v0.2

**Version 0.2 changes:** Added question 10 — Declaration Validity Conditions. This field was identified through external pressure-testing by Shawn Bullock (Continuity Science / HGCI), who observed that the v0.1 profile preserved declaration integrity and boundary integrity but did not yet ask what conditions must remain true for a declaration to stay valid over time. Question 11 (Reviewer-Use Limitation) renumbered from question 10.

---

## Purpose

The Seam Declaration Intake Profile is not an owner manifest standard.

It does not tell layer owners how to declare themselves. It does not define a required format for governance layer declarations. It does not certify, approve, or validate any owner's declared boundary.

It defines the minimum reviewer-side intake questions needed to compare independently authored governance artifacts without transferring authority between them.

Any declaration artifact — GLM manifest, README, boundary document, API specification, audit profile, policy statement, or any other form of owner-declared layer boundary — may be received by a reviewer using this profile. The profile is format-agnostic. The declaring owner retains full authority over their own declaration surface.

---

## Controlling Invariant

A reviewer may intake a declaration for comparison purposes. A reviewer may not convert that intake into ownership, certification, adoption, or authority over the declaring layer.

The intake profile preserves the question of what each layer declares. It does not answer whether those declarations are sufficient, correct, complete, or authoritative.

---

## Document Non-Claims

This profile does not:
- Define a required format for owner declarations
- Certify that any declaration is complete, accurate, or authoritative
- Transfer the declaring layer's authority to the reviewer or to any other layer
- Constitute adoption of the Seam Discipline by the declaring layer
- Replace, supersede, or supplement the declaring layer's own canonical boundary document
- Create obligations on layer owners who have not chosen to participate
- Determine legal compliance, regulatory sufficiency, or conformity assessment
- Become a conformance standard or certification mechanism

---

## The Eleven Intake Questions

A reviewer receiving any independently authored governance artifact applies the following eleven intake questions. The answers are recorded for reviewer-side comparison purposes only.

---

### 1. Artifact Identity

What artifact is being received?

- Artifact name or title
- Version or date, if declared
- Format (GLM manifest, boundary document, README, specification, policy statement, other)
- Location or URI where the artifact was obtained
- Hash of the artifact at time of intake, if computable

*Purpose: establish which specific artifact is being compared, not which layer the reviewer believes the artifact represents.*

---

### 2. Declaring Owner

Who declared this artifact?

- Organization or individual identified as the declaring owner
- Contact or canonical domain, if declared
- Whether the artifact is self-declared or attributed by a third party

*Purpose: preserve attribution without the reviewer speaking for the declaring owner. If the declaring owner is unknown or disputed, that must be recorded as a gap, not resolved by inference.*

---

### 3. Claimed Function

What does the declaring owner state this layer or artifact does?

- The stated primary function, in the declaring owner's own words where possible
- The timing position (pre-bind, at-bind, post-bind, cross-cutting, or undeclared)
- The operational scope as declared

*Purpose: record what was claimed, not what the reviewer infers the layer does. The reviewer does not restate or summarize the claiming owner's function. Verbatim or close-verbatim quotation is preferred.*

---

### 4. Explicit Non-Claims

What does the declaring owner explicitly state this layer or artifact does not do?

- Non-claims as declared by the owner, in the owner's own words where possible
- Whether non-claims are formally stated or implied by scope limitation
- Whether non-claims are versioned or subject to change

*Purpose: preserve the declaring owner's own negative surface. The reviewer does not add, infer, or expand non-claims beyond what the owner declared. If non-claims are absent from the declaration, that is recorded as a gap.*

---

### 5. Timing Position

Where does this artifact sit relative to the consequential boundary?

- Pre-bind: conditions or history before consequence becomes possible
- At-bind: the moment of execution or consequence commitment
- Post-bind: evidence, closure, or review after consequence formed
- Cross-cutting: declared across multiple timing positions
- Undeclared: timing position not stated in the artifact

*Purpose: enable reviewer-side temporal alignment without the reviewer assigning a timing position the owner did not declare.*

---

### 6. Authority Boundary

What authority does this artifact carry, and what authority does it explicitly disclaim?

- What the artifact authorizes, permits, or certifies, as declared
- What the artifact explicitly does not authorize, permit, or certify, as declared
- Whether the artifact declares itself as binding, advisory, evidential, or descriptive
- Whether the artifact claims enforcement capability

*Purpose: preserve the declared authority boundary so that reviewer-side comparison does not silently expand or contract it.*

---

### 7. Evidence Status

What evidentiary status does the declaring owner assign to this artifact?

- Self-declared: the layer owner describes their own layer
- Third-party witnessed: an independent party has attested to conditions described
- Machine-generated: produced by an automated system with or without human review
- Mixed: combination of the above
- Undeclared: evidentiary status not stated

*Purpose: a reviewer must not treat a self-declared boundary document as independent witness evidence, or treat a witnessed record as a self-declaration. The distinction matters for how the artifact is used in comparison.*

---

### 8. Composition Constraints

What does the declaring owner state about how this artifact or layer composes with others?

- Declared compatible layer types, if any
- Declared incompatible layer types, if any
- Declared sequencing requirements, if any
- Whether the artifact declares itself as a prerequisite, dependency, or independent layer
- Whether composability is declared unilaterally or requires mutual declaration

*Purpose: record the owner's declared composition posture without the reviewer inferring or expanding it.*

---

### 9. Known Divergence Risks

What conditions would cause this artifact to produce a Divergence Event Record when compared with other artifacts in a composed path?

- Fields or claims the reviewer expects may not align with adjacent artifacts
- Timing position conflicts with other layers in the same path
- Non-claims that may conflict with claims made by other layers
- Gaps between the declaration and the minimum emission standard required by the Correlation Contract

*Purpose: flag divergence risks before reviewer-side stitching begins, so that gaps are named explicitly rather than silently absorbed.*

---

### 10. Declaration Validity Conditions

What conditions must remain true for this declaration to remain valid?

- Conditions the declaring owner states are required for the declaration to hold — technical, organizational, policy, or operational
- External conditions, if changed, that would require revalidation, amendment, or withdrawal of the declaration
- Whether the declaring owner has specified a revalidation trigger, expiry, or staleness condition
- Whether the declaration has a declared review cadence or update mechanism

*Purpose: preserve the reality-continuity conditions underlying the declaration without making the intake profile a continuity layer or a judge of reality alignment. A declaration can remain internally coherent while the conditions it was built on have changed. Recording the declared validity conditions makes that drift visible to a reviewer without the intake profile itself enforcing or resolving it. This field records what the declaring layer said must remain true — not whether it currently does.*

---

### 11. Reviewer-Use Limitation

What must the reviewer not do with this intake record?

Every intake record produced under this profile must carry the following standing limitation:

*This intake record is a reviewer-side summary for comparison purposes only. It does not speak for the declaring layer. It does not constitute adoption of the Seam Discipline by the declaring layer. It does not transfer, expand, or certify the declaring owner's boundary. The declaring owner's canonical document remains the sole authoritative source for that layer's declared boundary.*

---

## Using This Profile with the Seam Discipline

The Declaration Intake Profile connects to the Seam Discipline's Correlation Contract at the intake boundary.

Before a reviewer applies the ALIGN, COMPARE, or ATTEST operations to any artifact, the artifact should be received through the Declaration Intake Profile. The intake record answers the minimum questions needed to treat the artifact as an independently declared artifact rather than an assumption.

The intake record does not become part of the declaring owner's artifact. It is a reviewer-side document that lives in the reviewer's bundle alongside the Correlation Contract operations.

If the declaring owner has published a machine-readable manifest — in GLM format or any other format — the reviewer uses that manifest as the source for intake questions 3, 4, 5, 6, 7, 8, and 10. The manifest is not replaced or supplemented by the intake record. The intake record only organizes what the manifest declares into the reviewer's comparison surface.

---

## Relationship to Other Seam Discipline Artifacts

| Artifact | Relationship |
|---|---|
| Non-Collapse Invariant List | The intake profile operationalizes I10: non-claims do not propagate by reference. The reviewer records the owner's non-claims; does not inherit them. |
| Correlation Contract | The intake profile feeds the minimum fields needed for ALIGN. Intake answers questions 3–8 before ALIGN begins. |
| Divergence Event Record | Intake question 9 pre-identifies divergence risks. If comparison produces a mismatch, the DER records it. |
| Layer Non-Claims Matrix | The matrix records what each layer does not do. The intake profile is how a reviewer receives a new layer's declaration before it could appear in the matrix — and only with owner authorization. |
| Review Bundle Map | The intake record may be listed in Section 2 of the Review Bundle Map as a reviewer-side artifact associated with a specific artifact in the composed path. |

---

*Seam Discipline — Declaration Intake Profile v0.2*
*Reviewer-Side Intake Rubric for Independently Authored Governance Artifacts*
*ASRO™ is a trademark of MagicianzCardstock LLC. Serial No. 99827630.*
