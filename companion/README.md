# Seam Discipline — Companion Layer Directory

AI governance is being built in layers.

Identity. Authorization. Execution control. Observability. Attestation. Adversarial verification. Audit. Policy translation. Institutional deployment. Post-execution continuity.

Different builders. Different functions. Different authority boundaries.

The problem is not that these layers exist independently. The problem is that there is no neutral place where they can become discoverable to each other without one absorbing the rest.

This directory is that place.

---

## What this is

The Companion Layer Directory is a public map of independently built governance, evidence, runtime, continuity, reliability, and accountability layers that may be compared under the Seam Discipline.

Any layer working on any part of the AI governance stack can declare its boundary here — in its own terms, at its own pace, without adopting ASRO, without joining a coalition, and without transferring authority to anyone else.

**The benefit is discoverability without absorption.**

Researchers, builders, reviewers, auditors, regulators, and procurement teams looking at the AI governance stack can find your layer, understand what it claims and does not claim, and see where it sits — without anyone implying endorsement, merger, certification, or authority transfer.

---

## What a Companion Layer Profile declares

A profile lets a layer owner state, in their own terms:

- what their layer observes
- what evidence it produces
- what authority it claims
- what authority it explicitly does not claim
- what reviewers may infer from its artifacts
- what reviewers must not infer
- what conditions must remain true for the declaration to stay valid

The profile answers these questions using the Seam Discipline Declaration Intake Profile v0.2 as its structure. It does not need to follow a rigid format — it needs to make the declaring layer's boundary independently readable.

---

## What inclusion does not mean

Inclusion in this directory does not imply:

- endorsement by James Aull or MagicianzCardstock LLC
- certification that the layer meets any standard
- adoption of the Seam Discipline by the declaring layer
- merger with ASRO or any other framework
- interoperability approval or technical validation
- investment recommendation
- authority transfer of any kind

Each profile is a self-declaration. The Seam Discipline preserves the question of what each layer declares. It does not answer whether those declarations are sufficient, correct, or authoritative.

---

## The guiding principle

> Comparison without collapse.

Companion profiles let adjacent systems be compared without being converted.

---

## How to submit a profile

Complete a Companion Layer Profile using the Declaration Intake Profile v0.2 field structure:

1. Artifact Identity
2. Declaring Owner
3. Claimed Function
4. Explicit Non-Claims
5. Timing Position
6. Authority Boundary
7. Evidence Status
8. Composition Constraints
9. Known Divergence Risks
10. Declaration Validity Conditions
11. Reviewer-Use Limitation

Submit to james@aisystemsreliability.org with "Companion Layer Profile" in the subject line. Profiles are listed publicly only with explicit owner authorization. If a layer owner does not authorize public listing, the profile is not added to the repository.

---

## Directory structure

```
companions/
├── README.md
└── profiles/
    └── (publicly authorized profiles go here)
```

---

## Currently listed profiles

| Layer | Profile |
|---|---|
| Governed-State Attestation | [ASRO — AI Systems Reliability Operator](./profiles/asro_companion_profile.md) |

---

## Canonical field names

When referencing Seam Discipline correlation fields in a profile, use:

- `decision_correlation_id`
- `event_window`
- `scope_hash`
- `artifact_hash`
- `alignment_determination_basis`

---

*Seam Discipline — Companion Layer Directory*
*ASRO™ is a trademark of MagicianzCardstock LLC. Serial No. 99827630.*
