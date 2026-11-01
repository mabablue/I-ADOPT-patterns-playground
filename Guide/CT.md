## 3. Field Specification: Constraint Types (CT)

| Field Name | Description | Value / Format | Required | Multiplicity |
| :--- | :--- | :--- | :---: | :---: |
| **`type`** | Top-level entity class. | Fixed: `Constraint Type` | **Yes** | No |
| **`subtype`** | Target component constrained. | `Property Constraint`, `ObjectOfInterest Constraint`, or `Matrix Constraint` | **Yes** | No |
| **`id`** | Persistent constraint identifier link. | `[CT<ID>](URL)` | **Yes** | No |
| **`name`** | Short name for constraint role. | String (e.g., `reference`, `depth`) | **Yes** | No |
| **`comment`** | Functional explanation of constraint role. | Text string | **Yes** | No |
| **`design`** | Application scope or target role. | String (e.g., `measurement`) | **Yes** | No |
| **`gh_issue`** | GitHub issue reference link. | `[issue #<ID>](URL)` | No | No |

### Markdown Template (CT<ID>.md)

- type: Constraint Type
- subtype: <Property|ObjectOfInterest|Matrix> Constraint
- id: [CT<ID>](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/pattern/CT<ID>.md)
- name: <constraint_name>
- comment: <functional_comment>
- design: <design_scope_or_target>
- gh_issue: [issue #<ISSUE_NUM>](https://github.com/mabablue/I-ADOPT-examples-playground/issues/<ISSUE_NUM>)
