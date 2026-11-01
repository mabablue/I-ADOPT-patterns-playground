## Field Specification: Variable Design Pattern (VDP)

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
