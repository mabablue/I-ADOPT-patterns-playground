## Field Specification: Mapping Rules (MR)

| Field Name | Description | Value / Format | Required | Multiplicity |
| :--- | :--- | :--- | :---: | :---: |
| **`type`** | Entity class. | Fixed: `Mapping Rule` | **Yes** | No |
| **`id`** | Mapping identifier link. | `[MR<ID>](URL)` | **Yes** | No |
| **`title`** | Alignment title. | String (e.g., `Ratio vs Single`) | **Yes** | No |
| **`subject`** | Source pattern link. | `[<PATTERN_ID>](URL)` | **Yes** | No |
| **`mapping_predicate`** | Alignment predicate. | `exactMatch`, `broadMatch`, `narrowMatch`, `relatedMatch`, or `closeMatch` | **Yes** | No |
| **`object`** | Target pattern link. | `[<PATTERN_ID>](URL)` | **Yes** | No |

### Markdown Template (MR<ID>.md)

- type: Mapping Rule
- id: [MR<ID>](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/mapping/MR<ID>.md)
- title: <subject_label> vs <object_label>
- subject: [<PATTERN_ID>](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/pattern/<PATTERN_ID>.md)
- mapping_predicate: <exactMatch|broadMatch|narrowMatch|relatedMatch|closeMatch>
- object: [<PATTERN_ID>](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/pattern/<PATTERN_ID>.md)
