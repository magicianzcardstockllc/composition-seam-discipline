# Review Bundle Map v0.1
## Seam Discipline — Composition Seam Discipline

**Author:** Perplexity / Reviewer-Facing Playbook Design (Aull Protocol)
**Authority:** James Aull / MagicianzCardstock LLC
**Date:** May 27, 2026
**Status:** Canonical v0.1

---

## Document Non-Claims

*This Review Bundle Map does not certify that any layer in the composed path is compliant, correct, or safe. It does not authorize any action, decision, or continuation. It does not constitute a governance decision. It does not merge or interpret the artifacts it lists — interpretation is the reviewer's function. It is a navigation guide for independent reviewer-side stitching.*

*The existence of this Review Bundle Map, and the regularity with which such maps are produced and reviewed, must not be treated as evidence that the governed system is operating correctly or that continuation is warranted. This map documents what was reviewable at the time of production. It does not justify what happens next.*

---

## Section 1 — Scope and Parameters

**Map produced by:** [Reviewer identifier — human, auditor, or designated review system. Not a layer producer.]

**Schema version:** `review-bundle-map-v0.1`

**Decision correlation ID:** [The `decision_correlation_id` shared across all artifacts in this composed path. Must be a single UUID present in every artifact instance listed in Section 2. If any artifact carries a different UUID, that artifact is a candidate for `UNANCHORED_CORRELATION_ID` divergence — record in Section 4 before proceeding.]

**Event window:** [The `event_window` this map covers — start and end timestamps in ISO 8601 format. This window should correspond to the narrowest shared event window across all artifacts in Section 2.]

**Scope hash:** [The `scope_hash` of the deployment boundary document for this composed path.]

**Map produced timestamp:** [ISO 8601 timestamp of when this map was assembled.]

**Purpose:** To enable a third-party reviewer to locate, verify, and stitch the independently governed artifacts associated with a specific decision boundary or consequence path — without producer cooperation and without treating the map itself as a governance determination.

---

## Section 2 — Artifact Registry

*One row per artifact instance, not one row per layer. A single layer may appear in multiple rows if it produced multiple artifacts for the same composed path. Each artifact must be independently verified.*

*Verification status values: `independently_verified` | `verification_not_yet_performed` | `verification_failed`*

*If verification status is `verification_failed`, the Associated DER column must carry the `divergence_record_ref` of the Divergence Event Record recording the failure. This column must not be empty for any row with `verification_failed` status.*

| `layer_id` | Artifact Type | `decision_correlation_id` | `event_window` | `scope_hash` | `artifact_hash` | Artifact Retrieval URI | Verification Status | Associated DER |
|---|---|---|---|---|---|---|---|---|
| `asro-v0.2` | Witness Record | [UUID] | [start–end] | [sha256] | [sha256] | [uri] | `verification_not_yet_performed` | — |
| `flowsignal-v0.1` | Admissibility Record | [UUID] | [start–end] | [sha256] | [sha256] | [uri] | `verification_not_yet_performed` | — |
| `mir-v0.1` | Pre-Bind Record | [UUID] | [start–end] | [sha256] | [sha256] | [uri] | `verification_not_yet_performed` | — |

**Multi-artifact note:** If `asro-v0.2` produced both a Standard Profile and a Compact Hash Profile for the same event, both appear as separate rows with the same `layer_id` and `decision_correlation_id` but different `artifact_hash` values. The reviewer must independently verify each row.

**`decision_correlation_id` consistency check:** All UUIDs in this column must be identical. If any row carries a different UUID, that divergence must be recorded in Section 4 before the reviewer proceeds with stitching.

---

## Section 3 — Absent Artifacts

*This section is required. It must not be omitted. Omitting this section creates an implicit completeness claim, which this map does not make.*

*An absent artifact is information, not an error. The reviewer must determine whether any absent artifact is relevant to their specific review question. This map does not make that determination.*

**Layers with no artifact recorded for this composed path:**

[For each expected layer that produced no artifact for this event path, list: `layer_id` | Reason unavailable (if known) | Reviewer impact note]

*If all expected layers have artifacts recorded in Section 2, state explicitly:*

**"No absent artifacts for this composed path — all expected layers have at least one artifact in Section 2. This statement is a documented check, not a completeness certification."**

**Coverage note:** This map lists artifacts that were locatable at the time of production. It does not certify that the listed artifacts are complete, sufficient, or correct for any specific review purpose.

---

## Section 4 — Divergence Summary

*This section lists all Divergence Event Records associated with this composed path. If any DER has `resolution_status: unresolved`, that must be visible here. The reviewer must not need to open individual DERs to discover unresolved divergences.*

*If no DERs are associated with this composed path, state explicitly: "No Divergence Event Records associated with this composed path."*

| `divergence_record_ref` | `divergence_nature_code` | Artifacts Involved | `resolution_status` | `declared_response_authority_ref` |
|---|---|---|---|---|
| [DER UUID or "none"] | — | — | — | — |

**Status note:** `referred_to_declared_response_authority` is not equivalent to resolved. The divergence remains open until `closed_by_external_authority` is recorded. This map preserves the `resolution_status` value exactly as stated in the DER. It does not interpret what any status means for admissibility or continuation.

---

## Section 5 — Reviewer Instructions

*The reviewer performs these steps. This map provides the inputs. The map does not perform verification on the reviewer's behalf.*

*Failure handling applies to every step: if a step fails, record the failure in a Divergence Event Record, set the affected artifact's verification status to `verification_failed` in Section 2, and continue to the next step. A failed step does not determine whether any action is admissible, whether execution should proceed, or whether any party must act. That is outside the scope of this map.*

**Step 1 — Artifact hash verification:**
For each artifact in Section 2, retrieve the artifact at its Artifact Retrieval URI. Compute SHA-256 over the canonical serialization of the governed-state record content. Verify that this matches the `artifact_hash` in Section 2.

*On failure:* Set verification status to `verification_failed`. Record a DER with `divergence_nature_code: ARTIFACT_HASH_TARGET_MISMATCH`. Continue to Step 2.

**Step 2 — Scope document verification:**
For each artifact in Section 2, retrieve the scope document at its associated scope document URI. Compute SHA-256 and verify that this matches the `scope_hash` in Section 2.

*On failure — document unretrievable:* Record a DER with `divergence_nature_code: UNRETRIEVABLE_SCOPE_OBJECT`. Set verification status to `verification_failed`. Continue to Step 3.

*On failure — hash mismatch:* Record a DER with `divergence_nature_code: SCOPE_HASH_CONFLICT`. Set verification status to `verification_failed`. Continue to Step 3.

**Step 3 — Correlation ID consistency check:**
Confirm that the `decision_correlation_id` in every artifact row in Section 2 is identical.

*On failure:* Record a DER with `divergence_nature_code: UNANCHORED_CORRELATION_ID` for each artifact carrying a divergent UUID. Continue to Step 4.

**Step 4 — Event window isolation check:**
Check that the `event_window` values across all artifacts overlap and are narrow enough to isolate the same event.

*On failure — windows do not overlap:* Record a DER with `divergence_nature_code: EVENT_WINDOW_DISCONTINUITY`. Continue to Step 5.

*On failure — window overbroad:* Record a DER with `divergence_nature_code: OVERBROAD_EVENT_WINDOW`. Continue to Step 5.

**Step 5 — Divergence record review:**
Review all DERs listed in Section 4. For each DER, note the `resolution_status`. An unresolved divergence is information the reviewer must account for. It does not prevent the reviewer from proceeding.

*No failure state for this step.* The reviewer notes what they find and proceeds.

**Step 6 — Absent artifact review:**
Check Section 3. For each absent artifact, determine whether it is relevant to the reviewer's specific question. Record your determination in the review record.

*No failure state for this step.* Absent artifacts are information.

**Step 7 — Non-authorization statement:**
Do not treat the existence of this Review Bundle Map, the completion of these verification steps, the absence of `verification_failed` statuses, or the absence of unresolved DERs as authorization to proceed, evidence of compliance, or confirmation that the governed system was operating correctly. The map documents what was reviewable. The reviewer determines what it means.

---

## Section 6 — Standing Non-Claim

*This section is a prominent standalone requirement, not a footnote.*

**Reassurance Infrastructure Drift Non-Claim:**

The existence of this Review Bundle Map, and the regularity with which such maps are produced and reviewed, must not be treated as evidence that the governed system is operating correctly or that continuation is warranted. The review ritual must not substitute for interruption pressure. This map documents what was reviewable at the time of production. It does not justify what happens next.

**Full Non-Claims Summary:**

This Review Bundle Map:
- Does not certify that any artifact is correct, sufficient, or compliant
- Does not authorize execution, continuation, or consequence binding
- Does not constitute a governance decision
- Does not determine admissibility of any action
- Does not merge layer artifacts into a unified governance record
- Does not perform stitching on the reviewer's behalf
- Does not resolve any divergence listed in Section 4
- Does not determine whether absent artifacts are required
- Does not determine what a failed verification step means for admissibility
- Does not become continuation permission through repeated production or review

---

## Section 7 — Map Integrity

**Non-claims propagation note:** Citing this Review Bundle Map does not satisfy any layer's obligation to state its own non-claims. Each layer must carry its own non-claims block in its own artifact. Reference is not delegation.

**Schema version:** `review-bundle-map-v0.1`

**Canonical serialization rule for `map_integrity_hash`:**

The `map_integrity_hash` is computed as follows:
1. Serialize the complete map content as canonical JSON using deterministic alphabetical key ordering, UTF-8 encoding, no insignificant whitespace.
2. Set the `map_integrity_hash` field itself to an empty string (`""`) during serialization.
3. Compute SHA-256 over the serialized bytes.
4. Record the resulting hash in the `map_integrity_hash` field.

This rule mirrors the Correlation Contract's canonical serialization rule and makes the integrity hash independently reproducible by any reviewer without producer cooperation.

**Map integrity hash:** [SHA-256 hash computed per the rule above, populated after all other fields are final]

**Producing reviewer signature:** [Optional — reviewer identity and attestation if applicable]

---

*Review Bundle Map v0.1 — Canonical*
*Seam Discipline — Composition Seam Discipline*
*ASRO™ is a trademark of MagicianzCardstock LLC. Serial No. 99827630.*
