## Field Specification: Component Design Patterns (PDP, ODP, MDP)
Streamlined pattern definitions decouple property and object definitions from variable-level constraint and matrix bindings.

Field Name,Description,Value / Format,Required,Multiplicity
type,Top-level entity class.,Fixed: Design Pattern,Yes,No
subtype,Component pattern category.,"Property Design Pattern, ObjectOfInterest Design Pattern, or Matrix Design Pattern",Yes,No
id,Persistent component identifier link.,`[<PDP,ODP,MDP>](URL)`
name,Short human-readable name.,"String (e.g., nominal, ratio, single)",Yes,No
definition,Formal semantic definition.,Text string,Yes,No
design,Conceptual component rule.,"Text string (e.g., The property must be specific.)",Yes,No
gh_issue,GitHub issue reference link.,[issue #<ID>](URL),No,No

### Markdown Template (<TYPE><ID>.md)

- type: Design Pattern
- subtype: <Property|ObjectOfInterest|Matrix> Design Pattern
- id: [<PDP|ODP|MDP><ID>](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/pattern/<PDP|ODP|MDP><ID>.md)
- name: <pattern_name>
- definition: <definition_text>
- design: <design_rationale>
- gh_issue: [issue #<ISSUE_NUM>](https://github.com/mabablue/I-ADOPT-examples-playground/issues/<ISSUE_NUM>)
