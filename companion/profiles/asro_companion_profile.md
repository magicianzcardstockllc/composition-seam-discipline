# ASRO — Companion Layer Profile
## AI Systems Reliability Operator

**Declaring Owner:** James Aull / MagicianzCardstock LLC
**Date:** June 2026
**Status:** Canonical self-declaration
**Profile version:** v0.1

---

AI systems can be silently modified after deployment — policies changed, tool permissions expanded, runtime configurations altered — without any external record of the change. The parties relying on those systems have no mechanism to verify that the governance state they were told existed was actually in place when the system acted.

ASRO was built to close that gap.

It does one thing: it preserves independently reviewable evidence of the governed state active when an AI system operated — so that a party outside the deploying system's trust boundary can examine what authority posture, policy state, tool access, and oversight conditions existed at the moment consequence became possible, without relying on the deploying system's own account of itself.

ASRO is not an enforcement layer. It does not authorize, certify, or control. It witnesses and preserves — and it does so from outside the system being governed.

---

## 1. Artifact Identity

**Name:** ASRO — AI Systems Reliability Operator
**Version:** v0.2 (current canonical release)
**Format:** Open specification — public GitHub repository
**Location:** https://github.com/magicianzcardstockllc/asro
**Trademark:** ASRO™ is a trademark of MagicianzCardstock LLC. USPTO Serial No. 99827630.

---

## 2. Declaring Owner

**Organization:** MagicianzCardstock LLC (Michigan)
**Individual:** James Aull, Founder
**Declaration type:** Self-declared canonical specification
**Contact:** james@aisystemsreliability.org
**Repository:** github.com/magicianzcardstockllc

---

## 3. Claimed Function

ASRO preserves independently reviewable evidence of the governed state active when an AI system operated — the authority posture, policy state, tool access, oversight conditions, model and context state, timestamps, hashes, and boundary context present when consequence became possible.

ASRO's primary function is to make the governed state of an AI deployment independently reviewable by a party outside the deploying system's trust boundary — without requiring that party to rely on the deploying system's own logs, explanations, or attestations.

**Timing position:** At-bind and pre-bind. ASRO captures governed-state evidence at or before the moment consequence becomes possible. It is not a post-execution reconstruction layer.

**Operational scope:** AI deployment governance, independently checkable attestation, governed-state evidence preservation, reviewer-side evidence preservation.

---

## 4. Explicit Non-Claims

ASRO does not:

- declare agent identity or validate agent credentials
- authorize AI deployment or issue deployment certificates
- control AI execution at runtime
- intercept, block, or modify AI actions
- certify model safety, alignment, or correctness
- determine legal compliance or regulatory sufficiency
- evaluate whether a governed state was adequate, sufficient, or appropriate
- assign responsibility, fault, or liability
- decide admissibility of evidence in any legal or regulatory proceeding
- enforce oversight or mandate human intervention
- become a compliance gate or prerequisite for AI system operation
- claim authority over layers it witnesses alongside
- certify that a composed path involving ASRO evidence is compliant, authorized, or safe
- replace external governance review, legal review, or institutional accountability

---

## 5. Timing Position

**Primary:** At-bind — ASRO captures the governed state at the moment consequence becomes possible, not after execution has completed.

**Secondary:** Pre-bind — ASRO can preserve formation-state evidence (what was declared before deployment) for later comparison against deployment-time conditions.

**Not:** Post-bind reconstruction. ASRO does not rebuild governed state from logs after the fact. If the evidence was not captured at the boundary, ASRO cannot produce it.

---

## 6. Authority Boundary

**What ASRO claims:**
- The ability to produce independently reviewable evidence of declared governed-state conditions at the decision boundary
- The ability to make that evidence independently verifiable by a party outside the deploying system's trust boundary
- The ability to identify and preserve divergence evidence between declared and observed governed-state conditions

**What ASRO explicitly does not claim:**
- Authority over any other layer in a composed governance path
- The ability to certify, authorize, enforce, or resolve the governed-state conditions it witnesses
- The ability to determine whether a system's governed state was sufficient for consequence
- Enforcement capability of any kind

**ASRO is advisory, evidential, and descriptive — not binding, authoritative, or controlling.**

---

## 7. Evidence Status

**Profile status:** Self-declared companion profile.

**ASRO evidence design:** Third-party witness evidence — ASRO is designed to operate outside the deploying system's trust boundary, producing evidence that does not rely on the system's own self-report.

**Limitation:** ASRO's independence depends on the integrity of the witness infrastructure. If the witness layer is controlled by or co-located with the system being witnessed, independence is reduced. This is a known architectural constraint named in the ASRO threat model.

---

## 8. Composition Constraints

**Compatible layer types:** ASRO is designed to compose reviewer-side with:
- Agent identity and declaration layers
- Deployment authorization layers
- Execution control layers — ASRO witnesses; execution control decides
- Operational observability layers
- Adversarial verification layers — ASRO provides the governed-state record that adversarial testing verifies against

**Sequencing:** ASRO does not require other layers to be present at runtime. Reviewer-side stitching occurs after capture, not during execution.

**Independence requirement:** ASRO must not absorb another layer's authority, non-claims, or evidence surface. Composition is reviewer-side only. No layer inherits authority from ASRO by association.

---

## 9. Known Divergence Risks

- **Self-attestation gap:** A system that controls its own ASRO witness produces circular evidence. The threat model names this as the primary adversarial vector.
- **Reconstruction risk:** Evidence captured post-execution rather than at-bind is not ASRO evidence — it is reconstruction. Reviewers must verify witness timestamps against execution timestamps.
- **Non-claims drift:** ASRO's non-claims may be misread as permissions or certifications. The non-claims block is mandatory on every artifact to prevent this.
- **Authority inheritance:** Reviewers combining ASRO evidence with other layer outputs may infer joint certification. The Seam Discipline's non-collapse invariants are designed to prevent this.
- **Completeness misread:** A complete ASRO record does not certify that governance was adequate — only that governed-state conditions were present and recorded.

---

## 10. Declaration Validity Conditions

This declaration remains valid under the following conditions:

- ASRO operates outside the trust boundary of the system being witnessed
- Witness timestamps are cryptographically bound at or before the execution boundary, not reconstructed afterward
- The hash and commitment infrastructure remains independently retrievable by a party outside the deploying system
- Policy state, authority posture, and tool access records are drawn from sources independent of the system's own self-report where possible
- The ASRO specification remains at v0.2 or is superseded by a version that explicitly carries forward these non-claims

**Revalidation triggers:**
- Any change to ASRO's architecture that moves witness capture inside the deploying system's trust boundary
- Any change that introduces post-execution reconstruction as a substitute for at-bind capture
- Any expansion of ASRO's claimed function to include authorization, enforcement, admissibility determination, or compliance certification

---

## 11. Reviewer-Use Limitation

This companion profile is a self-declaration by James Aull / MagicianzCardstock LLC. It does not constitute:

- certification that ASRO is compliant with any standard
- endorsement of any other layer listed in this directory
- a claim that ASRO solves the complete AI governance problem
- authority over any other layer that appears alongside ASRO in a composed governance path

*This profile is a reviewer-side summary for comparison purposes. The ASRO canonical specification at github.com/magicianzcardstockllc/asro remains the sole authoritative source for ASRO's declared boundary.*

---

*ASRO — Companion Layer Profile v0.1*
*James Aull / MagicianzCardstock LLC*
*ASRO™ is a trademark of MagicianzCardstock LLC. Serial No. 99827630.*
