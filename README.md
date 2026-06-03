# Seam Discipline

AI governance is fragmenting into layers.

Identity layers. Authorization layers. Execution control. Observability. Attestation. Audit. Policy translation. Institutional deployment. Continuity. Each one solving a real problem. None of them designed to work with the others without one absorbing the rest.

The Seam Discipline is the methodology that keeps them comparable without collapsing them.

It defines a small canonical artifact stack for comparing, correlating, and reviewing governance records across independently bounded layers — preserving each layer's sovereignty, non-claims, and evidentiary limits. When two governance layers need to be understood together, the Seam Discipline gives reviewers the tools to do that without letting one layer inherit authority from another.

**The controlling invariant:**

> *Divergence detection is not response authority assignment. The discipline preserves the question; it does not answer it.*

---

## The problem this solves

Most AI governance frameworks address one layer well while leaving adjacent layers unresolved. A system can have verified agent identity, a valid deployment certificate, runtime execution controls, and comprehensive operational logs — and still operate in ways that are not independently reviewable at the moment consequence becomes possible.

The gap is not in any single layer. It is in the absence of a neutral methodology allowing these layers to remain interoperable without any one layer absorbing the others.

When two governance layers are compared without a discipline governing that comparison, one of two things happens: they blur into a single authority surface, or the comparison produces conclusions neither layer was designed to support. Both outcomes undermine the independence that makes each layer valuable.

The Seam Discipline prevents that collapse.

---

## What this is

A set of invariants and minimal artifacts that enable reviewer-side stitching of independently governed AI governance artifacts — preserving each layer's sovereignty, preventing authority inheritance, and ensuring divergence remains detectable without enforcement.

The discipline is designed for AI governance, auditability, attestation, evidentiary review, and interoperability research where multiple independently governed artifacts need to remain comparable without becoming a shared control layer.

---

## What this is not

- a runtime enforcement layer
- a federation controller
- a certification system
- a compliance standard
- a shared authority layer
- a permission or continuation mechanism
- a replacement for external governance review
- a decision system for determining which layer is correct

---

## The artifact stack

**1. Non-Collapse Invariant List v0.1**
The rules that prevent comparison from becoming absorption. Defines the invariants that stop layer authority from drifting across governance boundaries when artifacts are composed together.

**2. Correlation Contract v0.1**
The minimal shared fields and reviewer-side operations needed to align and compare artifacts without merging authority surfaces. ALIGN, COMPARE, ATTEST — reviewer-side only.

**3. Divergence Event Record v0.5.1**
A passive, non-enforcement record for preserving structural mismatch when governed artifacts do not compose cleanly. Records the divergence. Does not resolve it.

**4. Layer Non-Claims Matrix v0.1**
The explicit negative space for each layer in a composed system — what each layer does not decide, authorize, enforce, or certify. External-layer rows require owner authorization before inclusion.

**5. Review Bundle Map v0.1**
The reviewer-facing navigation guide for locating artifacts, identifying absent artifacts, reviewing divergence records, and protecting against reassurance drift.

**6. Declaration Intake Profile v0.2**
The minimum reviewer-side intake questions needed to receive any independently authored governance artifact for comparison without transferring authority over the declaring layer. Includes Declaration Validity Conditions — what must remain true for a declaration to stay valid over time.

---

## The Companion Layer Directory

The Seam Discipline now includes a public Companion Layer Directory.

Builders working on any layer of the AI governance stack — identity, authorization, execution control, observability, attestation, adversarial verification, audit, policy translation, institutional deployment, post-execution continuity — can declare their boundary in their own terms and become discoverable to adjacent layers.

**The benefit is discoverability without absorption.**

A completed Companion Layer Profile lets researchers, builders, reviewers, auditors, regulators, and procurement teams find your layer, understand what it claims and does not claim, and see where it sits in the broader governance stack — without implying endorsement, merger, certification, or authority transfer.

See `/companions/README.md` to learn more or submit a profile.

---

## The Living Governance Stack Map

The `/stack-map/` folder contains a living map of the ten governance layer positions, the unsolved question each layer addresses, and the remaining gap in each layer that the field has not yet closed.

It is a topology of the problem, not a solution. Layers are listed in the map only when the layer owner has explicitly authorized inclusion.

---

## Repository structure

```
composition-seam-discipline/
├── README.md
├── LICENSE
├── NOTICE.md
├── artifacts/
│   ├── Seam_Discipline_Non_Collapse_Invariant_List_v0.1.md
│   ├── Seam_Discipline_Correlation_Contract_v0.1.md
│   ├── Seam_Discipline_Divergence_Event_Record_v0.5.1.md
│   ├── Seam_Discipline_Layer_Non_Claims_Matrix_v0.1.md
│   ├── Seam_Discipline_Review_Bundle_Map_v0.1.md
│   └── Seam_Discipline_Declaration_Intake_Profile_v0.2.md
├── stack-map/
│   └── Seam_Discipline_Living_Governance_Stack_Map_v0.1.md
└── companions/
    ├── README.md
    └── profiles/
        └── asro_companion_profile.md
```

---

## Canonical field names

- `decision_correlation_id`
- `event_window`
- `scope_hash`
- `artifact_hash`
- `alignment_determination_basis`

---

## License

Released under the [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/) (CC BY 4.0).

**Attribution:** James Aull / MagicianzCardstock LLC

---

## Trademark notice

ASRO™ is a trademark of MagicianzCardstock LLC. USPTO Serial No. 99827630.

Use of the Seam Discipline artifacts does not grant rights to use the ASRO™ trademark except as permitted by applicable trademark law or with permission from MagicianzCardstock LLC.

---

## Citation

> Aull, James. *Seam Discipline: Composition Seam Discipline v0.1.* MagicianzCardstock LLC, 2026.

---

## Maintainer

James Aull / MagicianzCardstock LLC
