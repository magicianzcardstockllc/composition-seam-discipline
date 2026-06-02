# Correlation Contract v0.1
## Seam Discipline — Operational Artifact Specification

**Author:** Venice (Aull Protocol)
**Authority:** James Aull / MagicianzCardstock LLC
**Date:** May 27, 2026
**Status:** Canonical v0.1

---

## 1. Purpose and Scope

The Correlation Contract defines the minimal shared surface that enables reviewer-side stitching of independently governed artifacts without layer-native upstream awareness, semantic absorption, or authority inheritance.

**Scope:** Single-deployer contexts where independently bounded governance layers produce artifacts that must remain comparable and reviewable after the fact.

**Cross-Deployer Exclusion:** Multi-deployer consequence synchronization is out of scope for Correlation Contract v0.1 and is handled in the Cross-Deployer Seam Note.

**Explicit Non-Scope:**
- This contract does not define runtime coordination between layers
- This contract does not certify correctness, safety, or compliance of composed artifacts
- This contract does not authorize actions, decisions, or executions
- This contract does not create a central registry, coordinator, or conformance authority

---

## 2. Governing Invariants

The Correlation Contract operates under the Non-Collapse Invariant List. Key implications:

| Invariant | Implication for Contract |
|---|---|
| I1 — Non-Absorption | References (IDs, hashes, windows) only; no semantic import |
| I2 — Non-Collapse | Cross-layer comparison produces evidentiary records only; no trust boundary merging |
| I3 — Non-Inheritance | Valid correlation record does not constitute operational permission |
| I4 — Reviewer-Side Stitching | Correlation happens externally; layers remain semantically opaque to each other |
| I5 — Divergence Preservability | Mismatches are recorded, not adjudicated by the contract |
| I6 — Independent Verifiability | All referenced artifacts must be independently retrievable |
| I7 — Out-of-Scope Legibility | Gaps must be nameable |
| I8 — Minimum Stitchability | Every artifact must carry anchored fields (see Section 3) |
| I9 — Replay-Resistance | Downstream decisions bind cryptographically to specific evidence queries |
| I10 — Non-Claims Non-Propagation | Citing this contract does not transfer its non-claims |

---

## 3. Minimum Emission Standard

### 3.1 Presence Requirements

Every participating layer must emit the following fields in every governed-state artifact:

| Field | Format | Purpose |
|---|---|---|
| `decision_correlation_id` | UUID v4 | Shared index for event-bound stitching |
| `event_window` | ISO 8601 interval | Temporal bounds for event isolation |
| `scope_hash` | SHA-256 | Cryptographic bind to deployment boundary |
| `artifact_hash` | SHA-256 | Content-addressable reference to governed-state record |

### 3.2 Content Requirements (Semantic Anchoring)

Presence alone is insufficient. Fields must satisfy:

**`decision_correlation_id`:**
- Must be event-bound — generated at specific decision/consequence boundary
- Must be shared across all layers participating in that event (same UUID in ASRO records for same event)
- Must not be reused across different events or deployments

**`event_window`:**
- Must be bounded — explicit start and end timestamps
- Must be sufficiently narrow to isolate the specific event
- Must be independently verifiable without layer-internal clock access

**`scope_hash`:**
- Must reference an independently retrievable document defining the deployment boundary
- Hash must cover the complete scope definition
- Scope document must be available to reviewers without layer-internal access

**`artifact_hash`:**
- Must hash the governed-state record content, not the metadata envelope
- Hash algorithm must be specified (SHA-256 default)
- Must enable content-addressable retrieval of the complete artifact

---

## 4. Primitive Operations

The Correlation Contract defines exactly three operations. All other operations are explicitly excluded.

### 4.1 ALIGN

**Purpose:** Establish that two or more layer-native artifacts describe the same event/bind/decision without altering either record.

**Constraints:**
- ALIGN is read-only relative to layer-native state
- ALIGN does not validate semantic truth of layer claims
- ALIGN does not merge or transform layer artifacts

**Output field:** `alignment_determination_basis` — values: `documented_criteria | undetermined`

### 4.2 COMPARE

**Purpose:** Detect deltas between layer-native claims about shared referents.

**Constraints:**
- COMPARE records divergence; it does not resolve it
- COMPARE does not assign truth-values to layer claims
- COMPARE output is evidence, not instruction

### 4.3 ATTEST

**Purpose:** Witness-grade logging of the correlation act itself.

**Constraints:**
- ATTEST documents the correlation process
- ATTEST does not certify correctness of correlation
- ATTEST limitations must be explicit and complete

### 4.4 Explicitly Excluded Operations

| Excluded Operation | Rationale |
|---|---|
| TRANSFORM | No conversion of layer-native formats |
| VALIDATE | No truth-assignment to layer claims |
| ROUTE | No instruction-passing between layers |
| SYNC | No state synchronization — layers remain asynchronous |
| RESOLVE | No adjudication of divergences |
| ENFORCE | No blocking or gating of layer operations |

---

## 5. Correlation Record Schema

```json
{
 "$schema": "https://seam-discipline.org/schemas/correlation-contract-v0.1.json",
 "correlation_record": {
 "record_metadata": {
 "correlation_id": "uuid-v4",
 "schema_version": "correlation-contract-v0.1",
 "created_timestamp": "ISO-8601",
 "operator": {
 "type": "human|system",
 "identifier": "string"
 }
 },
 "input_artifacts": [
 {
 "layer_ref": "owner-authorized-layer-id",
 "artifact_ref": "layer-native-identifier",
 "decision_correlation_id": "uuid-v4",
 "event_window": {
 "start": "ISO-8601",
 "end": "ISO-8601"
 },
 "scope_hash": "sha256:...",
 "artifact_hash": "sha256:...",
 "retrieval_path": "uri"
 }
 ],
 "operations_performed": {
 "align": {
 "alignment_determination_basis": "documented_criteria|undetermined",
 "criteria_used": ["temporal_overlap", "scope_match", "correlation_id_match"],
 "notes": "string"
 },
 "compare": {
 "status": "congruent|divergent|incomparable",
 "dimensions_compared": ["temporal", "semantic", "procedural"],
 "delta_map": null,
 "comparison_notes": "string"
 }
 },
 "limitations": [
 "source_layer_native_uncertainty",
 "temporal_resolution_limits",
 "schema_version_mismatch",
 "operator_cognitive_limits"
 ],
 "non_claims": {
 "enforcement": "This record does not authorize, permit, or enforce any action",
 "certification": "This record does not certify correctness, safety, or compliance",
 "permission_inheritance": "Evidence in this record does not constitute operational permission",
 "reassurance": "Existence of this record does not imply continuation is safe or warranted"
 }
 }
}
```

---

## 6. Non-Enforcement Non-Claims Block

Every Correlation Record must carry the following explicit non-claims:

**N1 — No Enforcement Authority:** This Correlation Record possesses zero mechanism to block, halt, alter, inject, or permit active system execution. It is evidence of review, not instrument of control.

**N2 — No Certification:** This record does not certify that composed artifacts are correct, safe, compliant, or fit for purpose.

**N3 — No Permission Inheritance:** Downstream systems may not treat this record as implicit authorization to proceed, continue, or execute. Evidence is not permission.

**N4 — Reassurance Infrastructure Drift (Standing Non-Claim):** The existence of this Correlation Record, and the regularity with which such records are produced and reviewed, must not be treated as evidence that the governed system is operating correctly or that continuation is warranted. The review ritual must not substitute for interruption pressure. This record documents what was reviewable; it does not justify what happens next.

**N5 — Non-Claims Non-Propagation:** A layer citing this Correlation Record does not thereby inherit its non-claims.

---

## 7. Pressure-Test Requirements (Normative)

### 7.1 Layer Independence Test

Remove all Correlation Records from all systems and verify each layer continues to operate identically using only layer-native artifacts. If removal breaks layer operations, correlation has become infrastructural — this is failure.

### 7.2 Contradiction Preservation Test

The Correlation Contract must be capable of producing a record showing two artifacts are NOT stitchable, not only that they are stitchable. If the only output the contract can produce is "these artifacts are correlated," it is enforcing alignment, not witnessing it.

---

## 8. Governance Recursion Limit

**Recursion Depth: 1**

The Correlation Contract is not self-governing. There is no meta-correlation primitive that correlates Correlation Records. If correlation of correlations is needed, it is performed by a human reviewer using standard deliberative governance processes.

---

## 9. Relationship to ASRO

ASRO may produce one of the artifact types used as input to the Correlation Contract. ASRO does not own the Correlation Contract and does not become the correlation authority. The Correlation Contract treats ASRO artifacts as one independently verifiable surface among others.

---

*Correlation Contract v0.1 — Canonical*
*Seam Discipline — Composition Seam Discipline*
*ASRO™ is a trademark of MagicianzCardstock LLC. Serial No. 99827630.*
