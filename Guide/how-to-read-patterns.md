## How to use and read PATTERNS:
Use one PATTERN for each description component (apart from constraints for which more might be needed), guided by decision trees

A Pattern is a decomposition design guide including this information:

## 1. Field Specification Table

| Field Name | Description | Instructions / Values | Required | Multiplicity |
| :--- | :--- | :--- | :---: | :---: |
| **`type`** | Top-level classification of the schema pattern. | Fixed to `Variable Design Pattern`. | **Yes** | No |
| **`subtype`** | Granular classification within the main pattern type. | Specifies which I-ADOPT component is addressed (e.g., *Property Pattern*, *ObjectOfInterest*, *Matrix*, *Constraint*, *Variable*). | **Yes** | No |
| **`id`** | Unique, persistent global identifier (URI) for the pattern file. | Direct URL to the pattern file in the GitHub repository. | **Yes** | No |
| **`name`** | Short, human-readable label for the pattern. | e.g., `angle` | **Yes** | No |
| **`definition`** | Formal text description explaining physical/mathematical nature. | Details boundary rules separating this pattern from others. | **Yes** | No |
| **`design`** | Pragmatic modeling instructions for mapping into I-ADOPT. | Guidance on how components should be populated. | **Yes** | No |
| **`ObjectOfInterest`** | Target class expected for the `ObjectOfInterest` slot. | Options: `Entity`, `Asymmetric System (Num/Denom)`, `Asymmetric System (Source/Target)`, `Symmetric System (Part)`. | No | No |
| **`Matrix`** | Target class expected, if required, for the `Matrix` slot. | Options: `Entity`, `Asymmetric System (Num/Denom)`, `Asymmetric System (Source/Target)`, `Symmetric System (Part)`. | No | No |
| **`required_constraint`** | Constraint type required for validity. | Specifies mandatory constraint class. | No | No |
| **`constrained_component`** | Target component constrained by `required_constraint`. | Indicates which slot receives the constraint. | No | No |
| **`associated_patterns`** | List of links to related design patterns in repository. | Use GitHub file URIs as list entries. | No | **Yes** |
| **`associated_mappings`** | List of links to mappings defined in repository. | Use GitHub file URIs as list entries. | No | **Yes** |
| **`path`** | Tracking choices taken through Decision Tree to reach pattern. | Must be wrapped in quotes (`"..."`) for YAML safety. | No | No |
| **`alt_paths`** | Alternative Decision Tree paths leading to this pattern. | Must be wrapped in quotes (`"..."`) for YAML safety. | No | **Yes** |
| **`example`** | Real-world I-ADOPT variable short name demonstrating pattern. | Short string label. | No | No |
| **`gh_issue`** | URI link to issue discussion demonstrating pattern application. | Direct URL to GitHub issue. | No | No |

---

## 2. Formatting Guidelines (YAML)

* **Multiple Entries (Lists):**
  * Indent with two spaces followed by `- ` (e.g., `  - https://...`)
  * When no list entries exist, represent explicitly as empty list: `[]`
* **Single Entries:**
  * When no value is provided, represent explicitly as `null`
* **String Safety:**
  * Enclose decision tree paths (`path` and `alt_paths`) in double quotes (`"..."`) to prevent parsing errors due to special characters (`->`, `=>`, `:`, etc.).

---

## 3. Example YAML Definition

```yaml
type: Variable Design Pattern
subtype: Property Pattern
id: https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/pattern/VDP03.yaml
name: angle
definition: A ratio comparing two geometric properties that retains units (e.g., degrees, radians) because the comparison is made against an external, universal geometric constant (a full circle/rotation).
design: Use single entity in the object of interest.
ObjectOfInterest: Entity
Matrix: null
required_constraint: null
constrained_component: null
associated_patterns:
  - https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/pattern/VDP28.yaml
associated_mappings: []
path: "DT0:Units(T) -> DT2:Length(F) -> OtherFund(F) -> DT3:Ratio(T) -> Time(F) -> DifferentQuantities(F) -> DiffEntities(F) => VDP03"
alt_paths: null
example: angle of attack
gh_issue: https://github.com/mabablue/I-ADOPT-examples-playground/issues/104
```
