# How to Read and Use I-ADOPT Patterns

## How PATTERNS Relate to Each Other

<img width="1225" height="427" alt="image" src="https://github.com/user-attachments/assets/87bf4b6c-f82a-4735-8849-0ad8677593cf" />


The **Decision Trees (DT)** guide you to the appropriate **Variable Design Pattern (VDP)**.

A **Variable Design Pattern (VDP)** acts as the orchestrator. It contains the complete set of instructions for humans and machines to decompose a variable and formally links to:
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

## 1. Field Specification: Variable Design Pattern (VDP)

| Field Name | Description | Value / Format | Required | Multiplicity |
| :--- | :--- | :--- | :---: | :---: |
| **`type`** | Top-level entity class. | Fixed: `Design Pattern` | **Yes** | No |
| **`subtype`** | Granular pattern category. | Fixed: `Variable Design Pattern` | **Yes** | No |
| **`id`** | Persistent pattern identifier link. | `[VDP<ID>](URL)` | **Yes** | No |
| **`name`** | Short human-readable title. | String (e.g., `length ref`, `areal density`) | **Yes** | No |
| **`definition`** | Physical/mathematical definition. | Text string | **Yes** | No |
| **`design`** | Structural modeling instructions. | Text string | **Yes** | No |
| **`PDP`** | Target Property Design Pattern link. | `[PDP<ID>](URL)` or `null` | **Yes** | No |
| **`ODP`** | Target Object of Interest Pattern link. | `[ODP<ID>](URL)` or `null` | **Yes** | No |
| **`MDP`** | Target Matrix Design Pattern link. | `[MDP<ID>](URL)` or `null` | No | No |
| **`CT`** | Constraint Type attached at variable level. | `[CT<ID>](URL)` or `null` | No | No |
| **`associated_shacl`** | Path to SHACL shape definition. | Markdown link or `null` | No | No |
| **`associated_domain_pattern`** | Community pattern specializing this VDP. | `[VCP<ID>](URL)` or `null` | No | No |
| **`associated_mapping`** | Associated mapping rule link(s). | List of `[MR<ID>](URL)` or `null` | No | **Yes** |
| **`path`** | Decision tree trace reaching this pattern. | Quoted string (`"DT0:... => VDP..."`) | No | No |
| **`alt_path`** | Alternative decision tree trace. | Quoted string or `null` | No | No |
| **`gh_issue`** | GitHub issue reference link. | `[issue #<ID>](URL)` | No | No |

### Markdown Template (`VDP<ID>.md`)
```markdown
- type: Design Pattern
- subtype: Variable Design Pattern
- id: [VDP<ID>](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/pattern/VDP<ID>.md)
- name: <pattern_name>
- definition: <definition_text>
- design: <design_rationale_and_structure>
- PDP: [PDP<ID>](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/pattern/PDP<ID>.md)
- ODP: [ODP<ID>](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/pattern/ODP<ID>.md)
- MDP: null
- CT: null
- associated_shacl: null
- associated_domain_pattern: null
- associated_mapping: null
- path: "<decision_tree_path>"
- alt_path: null
- gh_issue: [issue #<ISSUE_NUM>](https://github.com/mabablue/I-ADOPT-examples-playground/issues/<ISSUE_NUM>)
