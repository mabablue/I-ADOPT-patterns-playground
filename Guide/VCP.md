## Field Specification: Variable Community Patterns (VCP)

| Field Name | Description | Value / Format | Required | Multiplicity |
| :--- | :--- | :--- | :---: | :---: |
| **`type`** | Top-level entity class. | Fixed: `Design Pattern` | **Yes** | No |
| **`subtype`** | Domain pattern category. | Fixed: `Variable Community Pattern` | **Yes** | No |
| **`id`** | Persistent community pattern identifier link. | `[VCP<ID>](URL)` | **Yes** | No |
| **`name`** | Domain-specific variable name. | String (e.g., `column content`) | **Yes** | No |
| **`definition`** | Definition within domain context. | Text string | **Yes** | No |
| **`domain`** | Scientific domain or community. | String (e.g., `atmospheric sciences`) | **Yes** | No |
| **`design`** | Applied decomposition choices. | Text string | **Yes** | No |
| **`PDP`** | Associated Property Pattern link. | `[PDP<ID>](URL)` | **Yes** | No |
| **`ODP`** | Associated Object of Interest Pattern link. | `[ODP<ID>](URL)` | **Yes** | No |
| **`MDP`** | Associated Matrix Pattern link. | `[MDP<ID>](URL)` or `null` | No | No |
| **`gh_issue`** | GitHub issue reference link. | `[issue #<ID>](URL)` | No | No |

### Markdown Template (VCP<ID>.md)

- type: Design Pattern
- subtype: Variable Community Pattern
- id: [VCP<ID>](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/pattern/VCP<ID>.md)
- name: <community_pattern_name>
- definition: <definition_text>
- domain: <scientific_domain>
- design: <design_rationale>
- PDP: [PDP<ID>](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/pattern/PDP<ID>.md)
- ODP: [ODP<ID>](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/pattern/ODP<ID>.md)
- MDP: [MDP<ID>](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/pattern/MDP<ID>.md)
- gh_issue: [issue #<ISSUE_NUM>](https://github.com/mabablue/I-ADOPT-examples-playground/issues/<ISSUE_NUM>)
