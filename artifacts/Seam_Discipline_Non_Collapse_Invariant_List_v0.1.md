# Non-Collapse Invariant List v0.1
## Seam Discipline — Composition Seam Discipline

**Author:** DeepSeek / Protocol Requirements & Architecture Synthesis (Aull Protocol)
**Authority:** James Aull / MagicianzCardstock LLC
**Date:** May 27, 2026
**Status:** Canonical v0.1

---

## Purpose

The Non-Collapse Invariant List defines what must never be inferred, inherited, transferred, or silently absorbed across seams between independently governed AI governance primitives. These invariants are the precondition for the Correlation Contract, the Divergence Event Record, the Review Bundle Map, and the Layer Non-Claims Matrix. If any invariant is violated, the seam has failed — regardless of how operationally coherent the composed output appears.

Each invariant is stated as a prohibition. Each carries a one-line non-claim that defines what the invariant does NOT do.

---

## The Invariants

### I1 — Non-Absorption

No layer may natively consume, interpret, or depend on another layer's internal semantics as part of its own authority surface.

Correlation is permitted — a layer may reference another layer's artifact by hash, identifier, timestamp, and scope. Absorption is not — a layer may not parse, validate, or incorporate another layer's findings as if they were its own.

**Non-claim:** This invariant does not require layers to be blind to each other's existence. It prohibits semantic ingestion. A layer may know that another layer produced an artifact. It may not treat that artifact's conclusions as its own.

---

### I2 — Non-Collapse

Composition of multiple layer artifacts must not produce a unified artifact in which individual layer boundaries are indistinguishable.

When artifacts from MIR, ASRO, and FlowSignal are brought together for review, each artifact must retain its own provenance, non-claims, layer identity, and independent verifiability. The composed record is a map, not a merger.

**Non-claim:** This invariant does not prohibit review bundles or correlation records. It prohibits the production of a single artifact that speaks with the combined authority of multiple layers without preserving per-layer attribution.

---

### I3 — Non-Inheritance

No layer may inherit authority, admissibility weight, or enforcement power from another layer's artifact.

A reference to another layer's record is a reference — not an elevation. If ASRO witnesses that policy v1.2 was active at bind-time, that witness record does not authorize FlowSignal to resolve ALLOW. FlowSignal must make its own admissibility determination.

**Non-claim:** This invariant does not prohibit layers from consuming each other's artifacts as inputs. It prohibits one layer treating another layer's finding as a substitute for its own decision.

---

### I4 — Reviewer-Side Stitching ★

The act of correlating artifacts across layers belongs to the external reviewer, not to any layer natively.

Layers may emit correlation IDs, timestamps, scope identifiers, and artifact hashes to enable stitching. They may not perform the stitching on the reviewer's behalf and present the result as a single layer output.

**Non-claim:** This invariant does not prohibit layers from emitting metadata that makes stitching possible. It prohibits layers from producing the stitched artifact as a layer output.

**★ Operational Warning:** I4 is the invariant most likely to be violated in practice. The pressure is architectural, operational, and commercial. Layers that emit metadata for reviewer stitching will be asked by users to produce the stitched view. The layer that complies has violated I4 regardless of whether the output is labeled "for reviewer convenience." No structural defense fully prevents this. The only durable defense is cultural: reviewers must insist on receiving raw artifacts and performing their own stitching.

---

### I5 — Divergence Preservability

When layer artifacts diverge — in scope, event window, declared state, or artifact reference — that divergence must be expressible and preservable as a record without any layer claiming authority to resolve it.

Divergence is evidence, not error. The Divergence Event Record preserves it. No layer — and no component of the Seam Discipline — decides which side is correct.

**Non-claim:** This invariant does not require that every divergence be flagged. It requires that divergence be recordable when detected.

---

### I6 — Independent Verifiability

Every artifact referenced in a composition must remain independently verifiable without access to any other layer's internal state, logs, or runtime.

The reviewer must be able to check Artifact A without asking Layer B to explain what Layer A meant. If verification requires the original producer to be present, online, and cooperative, the artifact is not independently verifiable.

**Non-claim:** This invariant does not require that every artifact be verifiable by any random third party. It requires that verification not depend on the continued cooperation of the artifact's producer.

---

### I7 — Out-of-Scope Legibility

Gaps between layers — topics, time windows, consequence paths not covered by any layer — must be nameable and present in the composed record without being silently absorbed into any layer's coverage claim.

The composed record must make these gaps visible. Incompleteness is part of what makes a composed record honest.

**Non-claim:** This invariant does not require that every possible gap be identified. It requires that gaps which are known or discoverable not be silently absorbed into adjacent layers' coverage claims.

---

### I8 — Minimum Stitchability Standard ★

Every layer artifact must carry a `decision_correlation_id`, a declared `event_window`, a `scope_hash`, and an `artifact_hash`. These fields must be present. Presence alone is not sufficient. The fields must be anchored:

- `decision_correlation_id` must be event-bound and shared across all participating layers in the same event path; a correlation ID generated independently per artifact without cross-layer sharing is an artifact identifier, not a correlation ID.
- `scope_hash` must reference an independently retrievable scope document; a hash of an inaccessible internal document is an integrity check, not a verification surface.
- `event_window` must be bounded tightly enough to isolate the referenced event; a 72-hour window that covers every event the layer has been involved in is not a window — it is an absence of constraint.
- `artifact_hash` must hash the governed-state record or layer-native artifact being referenced, not merely the metadata envelope.

Presence without anchoring satisfies the form of this invariant while defeating its function.

**Until the Correlation Contract is canonicalized, the anchoring requirements stated in this invariant are self-executing — presence without anchoring is a violation of this invariant regardless of whether the Correlation Contract has been published.**

**Non-claim:** This invariant does not prescribe the format or naming of correlation IDs, event windows, or scope identifiers. Those belong to the Correlation Contract. It defines the floor below which an artifact becomes reviewer-opaque, and it defines what makes that floor meaningful rather than merely present.

**★ Detection Limitation:** A layer that emits anchored fields but generates fresh, unshared correlation IDs per artifact satisfies the anchoring language while still producing unstitchable records. The reviewer must have access to at least one other artifact from the same event path to detect the violation. This is a structural limitation — not a wording failure, but a detection dependency that the Correlation Contract must close operationally.

---

### I9 — Replay-Resistance Binding

A downstream decision artifact that consumes layer evidence must cryptographically bind to the specific evidence query — by hash and timestamp — that it consumed. The same evidence cannot be silently reused for a different decision without a new query and a new decision artifact.

**Non-claim:** This invariant does not require that every decision artifact reference every piece of evidence it considered. It requires that evidence which is treated as dispositive be cryptographically bound to the decision artifact.

---

### I10 — Non-Claims Non-Propagation

A layer that cites another layer's non-claims does not thereby inherit, adopt, or satisfy those non-claims for its own artifact.

A downstream system saying "we reference ASRO which states DOES_NOT_DECIDE_ADMISSIBILITY" cannot use that reference to avoid its own admissibility determination. Each layer is responsible for its own non-claims. Reference is not delegation.

**Non-claim:** This invariant does not prohibit cross-referencing non-claims for reviewer clarity. It prohibits treating another layer's non-claims as a substitute for one's own.

---

## What This List Does Not Do

- Does not certify that any layer's output is correct, sufficient, or compliant
- Does not prescribe positive behavior — each invariant is a prohibition, not a design specification
- Does not create obligations between layers — no layer is required to enforce another layer's invariants
- Does not become a conformance checklist
- Does not replace the Correlation Contract, the Divergence Event Record, or the Layer Non-Claims Matrix — it is their constraint foundation, not their substitute

---

## Relationship to Other Artifacts

| Artifact | Relationship to This Document |
|---|---|
| Correlation Contract | Must satisfy I1, I4, I6, and I8. Must not violate I2, I3, I5, I7, I9, or I10. |
| Divergence Event Record | Must satisfy I5. Must not violate I3 or I10. |
| Layer Non-Claims Matrix | Must satisfy I10. Must not violate I1, I2, or I3. |
| Review Bundle Map | Must satisfy I2, I4, I6, and I7. Must not violate I3 or I10. |

---

*Non-Collapse Invariant List v0.1 — Canonical*
*Seam Discipline — Composition Seam Discipline*
*ASRO™ is a trademark of MagicianzCardstock LLC. Serial No. 99827630.*
