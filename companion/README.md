# companion/

This folder contains implementation support materials for the Seam Discipline v0.1.

These documents are not part of the canonical artifact stack. They are reviewer-playbook support materials intended to help implementers understand how the canonical artifacts work in practice.

## Contents

**Cold-test scenario** *(pending field-name normalization)*
A worked example using three mock artifacts — ASRO witness, FlowSignal admissibility record, EVIDE closure stub — demonstrating the Correlation Contract verification probe sequence, a simulated anchoring failure, and the resulting Divergence Event Record.

Field names in the cold-test scenario are normalized to the canonical underscore format from the Correlation Contract and DER v0.5.1 specs:
- `decision_correlation_id`
- `event_window`
- `scope_hash`
- `artifact_hash`
- `alignment_determination_basis`

---

*Companion materials are provided as-is for implementation guidance. They do not modify, override, or supersede the canonical artifact stack in the `/artifacts/` folder.*
