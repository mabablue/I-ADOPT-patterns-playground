# How to Read and Use I-ADOPT Patterns

## How PATTERNS Relate to Each Other

<img width="1225" height="427" alt="image" src="https://github.com/user-attachments/assets/87bf4b6c-f82a-4735-8849-0ad8677593cf" />


The **Decision Trees (DT)** guide you to the appropriate **Variable Design Pattern (VDP)**.

A **[Variable Design Pattern (VDP)](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Guide/VDP.md)** acts as the orchestrator. It contains the complete set of instructions for humans and machines to decompose a variable and formally links to:
- **Property Design Pattern (PDP)**: Defines requirements on the property being observed or quantified.
- **Object of Interest Design Pattern (ODP)**: Defines the entity or system structure (e.g., single entity, ratio, symmetric/asymmetric system).
- **Matrix Design Pattern (MDP)** *(optional)*: Defines the environmental or embedding matrix context when relevant.
- **Constraint Type (CT)** *(optional)*: Declares required qualifiers or reference points (e.g., reference, spatial, or temporal constraints).
- **Variable Community Pattern (VCP)** *(optional, domain-specific)*: Specializes or overrules the core VDP according to domain conventions (e.g., atmospheric sciences).
- **Mapping Rule (MR)** *(optional)*: Captures cross-pattern alignments, relationships, or community equivalences (`exactMatch`, `relatedMatch`, etc.).
- **SHACL Shapes (`associated_shacl`)** *(optional)*: Validates that instantiated variables conform to the selected pattern decomposition.

---

## How to Use and Read PATTERNS

Decompose variables using **one pattern per component role** (Property, Object of Interest, Matrix), supplemented by **Constraint Types** where needed.

Pattern files are written as flat bullet lists designed for direct GitHub browsing and navigation:
- Every internal pattern reference and GitHub issue must be an inline Markdown hyperlink: `[LABEL](URL)`.
- Use explicit `null` for unassigned single references.
- Use explicit bullet lists under a key when multiple entries are present.

---
