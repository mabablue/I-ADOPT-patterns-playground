## Glossary of I-ADOPT related concepts
with links to the [I-ADOPT ontology](https://w3id.org/iadopt/ont/Entity)


**[Constraint](https://w3id.org/iadopt/ont/Constraint)**

**Description components**: An I-ADOPT variable is decomposed into different components which have different roles in the variable description.

**[Entity](https://w3id.org/iadopt/ont/Entity)** with description roles: **[Object of Interest](https://w3id.org/iadopt/ont/hasObjectOfInterest)**, **[Matrix](https://w3id.org/iadopt/ont/hasMatrix)** and **[Context Object](https://w3id.org/iadopt/ont/hasContextObject)**

**[Property](https://w3id.org/iadopt/ont/Property)**

**[Statistical Modifier](https://w3id.org/iadopt/ont/StatisticalModifier)**

**Mapping**: describes how two different representations can be mapped to each other.

**[System](https://w3id.org/iadopt/ont/System)**: 
 - [Symmetric System](https://w3id.org/iadopt/ont/SymmetricSystem)
    - [hasPart](https://w3id.org/iadopt/ont/hasPart)
  - [Asymmetric System](https://w3id.org/iadopt/ont/AsymmetricSystem)
    - [hasNumerator](https://w3id.org/iadopt/ont/hasNumerator)/[hasDenominator](https://w3id.org/iadopt/ont/hasDenominator)
    - [hasSource](https://w3id.org/iadopt/ont/hasSource)/[hasTarget](https://w3id.org/iadopt/ont/hasTarget)

**[Variable](https://w3id.org/iadopt/ont/Variable)**

**Variable Design Pattern**: A pattern that provides a decomposition design guide by including this information:
  - id: a URL to the pattern
  - name
  - comment: description of the pattern
  - design: instructions how to model
  - instances: a list of examples
  - involved_components: involved description components
  - constrained_components
  - associated_patterns: other patterns that might be required using this pattern
  - associated_mappings: mapping patterns that can be used with this pattern
  - example: one example applying the pattern
  - gh_issue: one issue that shows the example
