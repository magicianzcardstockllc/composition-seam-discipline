# Seam Discipline — Living Governance Stack Map v0.1

**Authority:** James Aull / MagicianzCardstock LLC
**Date:** June 2026
**Status:** Living document — updated as adjacent layers are confirmed and authorized for listing

---

## Purpose

AI governance appears to require a modular stack of distinct layers. No single framework closes all gaps.

This map identifies the governance problem space by layer — the unsolved question each layer addresses, the specific gap that remains, and where the Seam Discipline enables comparison between layers without collapsing their boundaries.

Layers and adjacent work are listed here only when the layer owner has explicitly authorized inclusion. Unlisted layers remain open — the directory exists so builders working on any part of this stack can declare their boundary and become findable.

---

## The Problem This Stack Addresses

Most AI governance frameworks address one layer well while leaving adjacent layers unresolved. A system can have verified agent identity, a valid deployment certificate, runtime execution controls, and comprehensive operational logs — and still operate in ways that are not independently reviewable at the moment consequence becomes possible.

The gap is not in any single layer. It is in the absence of a neutral structure allowing these layers to remain interoperable without any one layer absorbing the others.

The Seam Discipline addresses the interoperability problem. Each layer in this stack addresses a distinct governance question. The Companion Layer Directory allows layers to declare their boundaries and become comparable without conversion, merger, or authority transfer.

---

## The Modular Governance Stack

---

### Layer 1 — Agent Identity and Declaration

**The unsolved question:** What is this agent, who validates its claims, and what authority does it carry — not just at credential issuance, but at the moment it acts?

**The remaining gap:** Verified identity infrastructure is maturing rapidly. Cryptographic credentials, W3C Decentralized Identifiers, verifiable credentials, and SPIFFE/SPIRE workload identity are active and in deployment. What identity infrastructure does not yet answer is whether the claimed authority conditions remain valid after identity is established. An agent can be cryptographically identified and still act outside its authorized scope. Identity verification closes the "who" question but leaves the "under what conditions" question open.

**Where this connects to the Seam Discipline:** A companion profile for an identity layer would declare what the layer proves — credential validity, delegation chain, capability assertions — and what it does not prove: that the authority posture claimed at credential time still held at execution time.

*No publicly listed companion profiles yet for this layer.*

---

### Layer 2 — Deployment Authorization

**The unsolved question:** Should this AI system be permitted to operate here, under these conditions, at this risk level — and can that determination be independently verified?

**The remaining gap:** Model cards, audits, and benchmark evaluations describe systems but do not produce binding deployment decisions with independently verifiable legal or financial force. Runtime authorization infrastructure addresses whether a specific action may proceed under current business policy and compliance constraints — but authorization at deployment time does not guarantee that conditions remain valid as the system operates, is updated, or encounters contexts outside its original deployment scope. The gap between "authorized to deploy" and "authorized to act in this specific context right now" is structurally unaddressed.

**Where this connects to the Seam Discipline:** A companion profile for a deployment authorization layer would declare what the deployment decision proves, under what conditions it remains valid, and what changes would require reauthorization — exactly the Declaration Validity Conditions field.

*No publicly listed companion profiles yet for this layer.*

---

### Layer 3 — Execution Control

**The unsolved question:** Does this system have valid authority to execute this specific action at this specific moment — and can that determination be independently held?

**The remaining gap:** Execution control infrastructure — runtime interception, authority-aware escalation, mandatory approval boundaries — is the most active development layer in 2026. The formal taxonomy of agentic risks including goal hijacking, tool misuse, identity abuse, and memory poisoning is now established. What execution control does not produce is independently reviewable evidence of the governed conditions that made the execution determination. A system can enforce a valid execution boundary and leave no independently verifiable record of the governed state that was active when it did so. In many implementations, the enforcer and the witness may be the same system.

**Where this connects to the Seam Discipline:** Execution control determines whether an action may proceed. Governed-state attestation preserves evidence of the conditions under which that determination was made. These are adjacent but distinct functions. A companion profile for an execution control layer would declare what it enforces and what evidence it produces — and explicitly what it does not produce.

*No publicly listed companion profiles yet for this layer.*

---

### Layer 4 — Operational Observability

**The unsolved question:** What did the system actually do during operation, and is that record independently verifiable?

**The remaining gap:** Organizations report high confidence in their ability to govern AI agents, yet research consistently finds that a near-majority of deployed agents are not actively monitored or secured — a structural gap between perceived control and operational reality. More fundamentally, operational logs are system-generated. They record what the system reports it did, not what governed state was active when it acted. Monitoring tells you what happened but not what authority posture, policy state, oversight condition, or tool permission was active at the moment an action became consequential. The observable artifact and the governed context that produced it are not the same record.

**Where this connects to the Seam Discipline:** Observability and governed-state attestation are adjacent but not identical. A companion profile for an observability layer would declare what the operational record proves and — critically — what a reviewer must not infer from it about the governed conditions surrounding the action.

*No publicly listed companion profiles yet for this layer.*

---

### Layer 5 — Governed-State Attestation

**The unsolved question:** What governed state was active when consequence became possible — and is that independently reviewable by a party outside the deploying system's trust boundary?

**The remaining gap:** AI governance is increasingly judged not by policy statements but by operational evidence. Courts, regulators, and auditors are beginning to ask for contemporaneous records of the governed conditions surrounding AI actions — not reconstructions from system logs after the fact. The structural gap is that most evidence of governed state is produced by the same system being governed. A host that controls its own attestation can selectively report, reconstruct, or omit governed-state evidence without detection. Independent witness infrastructure — evidence produced outside the deploying system's trust boundary — remains underdeveloped relative to the evidentiary demands that enforcement is beginning to create.

**This is ASRO's layer.** See the ASRO companion profile in `/companions/profiles/`.

**Listed companion profile:** [ASRO — AI Systems Reliability Operator](../companions/profiles/asro_companion_profile.md)

---

### Layer 6 — Adversarial Verification

**The unsolved question:** Does the governance stack hold under pressure — not just under normal conditions, but when an adversary is actively trying to circumvent it?

**The remaining gap:** Pre-deployment red-teaming and adversarial testing are established practices. What remains underdeveloped is runtime adversarial verification — continuous testing of whether governance infrastructure remains intact under live deployment conditions, as systems update, as deployment contexts shift, and as adversarial pressure evolves. A governance stack that passes pre-deployment testing may still fail silently under production conditions. The gap is between adversarial testing as a deployment gate and adversarial verification as an ongoing operational property.

**Where this connects to the Seam Discipline:** Governed-state attestation records provide the evidence base against which adversarial verification can test. A companion profile for an adversarial verification layer would declare what it tests, what its findings prove, and what a reviewer must not infer from a passing result.

*No publicly listed companion profiles yet for this layer.*

---

### Layer 7 — Cryptographic Audit

**The unsolved question:** Can governance evidence be independently verified after the fact — and does that verification extend to the governed state at execution time, not just the artifact that was produced?

**The remaining gap:** Cryptographic signing of model artifacts, datasets, and deployment records is maturing. Signing infrastructure proves that a recorded artifact has not been modified since signing. What it does not prove is that the signed record accurately captured the governed state that was active when the system acted — or that the governed state at signing time matched the governed state at execution time. A signed log is tamper-evident. It is not independently witnessed. The gap between tamper-evidence and independent witness is the structural distinction that most cryptographic audit infrastructure does not yet address.

**Where this connects to the Seam Discipline:** Cryptographic audit and governed-state attestation are adjacent but not equivalent. A companion profile for a cryptographic audit layer would declare what its signing and chaining proves, and explicitly what it does not prove about the governed conditions surrounding the signed events.

*No publicly listed companion profiles yet for this layer.*

---

### Layer 8 — Policy Translation

**The unsolved question:** Can governance evidence be translated into institutional policy, regulatory compliance, and procurement criteria that actually bind AI behavior in practice?

**The remaining gap:** Regulatory frameworks are enforcing faster than institutional translation can keep pace. As agentic AI shifts from producing outputs to taking actions — committing resources, initiating transactions, influencing high-stakes decisions — liability increasingly centers on the action rather than the output. The gap is not in the existence of governance frameworks but in the translation from technical evidence to institutional policy and procurement criteria that organizations can actually operationalize. Most governance frameworks work at the level of principle or standard. The operational layer connecting independently verifiable governed-state evidence to enforceable institutional accountability remains fragmented.

**Where this connects to the Seam Discipline:** A companion profile for a policy translation layer would declare what regulatory obligations it maps, what evidence it requires as inputs, and what a reviewer must not infer from a compliance mapping about the underlying governed state.

*No publicly listed companion profiles yet for this layer.*

---

### Layer 9 — Institutional Deployment

**The unsolved question:** Can the governance stack land in real institutions with real accountability structures — not just as a formal framework, but as an operational reality embedded in day-to-day workflows?

**The remaining gap:** Most large organizations now have formal AI governance structures — risk committees, governance teams, policy statements. Research consistently finds that formal governance structures have not kept pace with operational AI readiness. The foundations needed to operationalize governance — embedded processes, controls, tooling, and skills present in day-to-day work — lag significantly behind the formal architecture. The gap is between governance that exists on paper and governance that survives contact with institutional incentives, legacy systems, and organizational complexity.

**Where this connects to the Seam Discipline:** A companion profile for an institutional deployment layer would declare what it operationalizes, what organizational conditions it requires, and what a reviewer must not infer from institutional adoption about the underlying technical governed state.

*No publicly listed companion profiles yet for this layer.*

---

### Layer 10 — Post-Execution Semantic Continuity

**The unsolved question:** Does the meaning of the proof remain stable as organizational practice, incentives, exceptions, and institutional memory evolve over time?

**The remaining gap:** A system can preserve a valid governed-state record at execution time and still drift. The tolerance for semantic drift — conflicting definitions, inconsistent metrics, undocumented logic, evolving institutional assumptions — ran out the moment AI agents began acting on that data at scale. The failure mode is not that the record becomes invalid. It is that the record remains internally coherent while the reality it was originally describing has changed. The declaration keeps its authority boundary. The environment it was built on keeps moving. No single listed layer in this map currently owns whether the original governance intent remains intact over time.

**Where this connects to the Seam Discipline:** The Declaration Validity Conditions field — Question 10 of the Declaration Intake Profile — directly addresses this gap. It asks each declaring layer what conditions must remain true for its declaration to remain valid, and what changes would require revalidation. Post-execution semantic continuity is the layer that detects when those conditions have changed. The two are adjacent without being the same function.

*No publicly listed companion profiles yet for this layer.*

---

## How to Appear in This Map

If you are working on a governance-relevant layer and want your work listed here, complete a Companion Layer Profile (see `/companions/README.md`) and explicitly authorize public listing.

Appearance in this map requires explicit owner authorization. No layer is listed without it.

Appearance does not constitute endorsement, certification, adoption, or authority transfer.

---

*Seam Discipline — Living Governance Stack Map v0.1*
*ASRO™ is a trademark of MagicianzCardstock LLC. Serial No. 99827630.*
