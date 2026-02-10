# I-ADOPT Variable Design Guide


## Workflow:

1. Follow Variable Design Steps using decision trees leading to [patterns](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Guide/how-to-read-patterns.md)
2. Use the **[I-ADOPT Visualizer](https://sirkos.github.io/iadopt-vis/)** to compose your variable.
3. Find appropriate concepts and add the IRIs in the visualizer
4. Copy RDF and safe it as turtle (.ttl) file in the [I-ADOPT Examples Repository](https://github.com/mabablue/I-ADOPT-examples-playground)
5. Create an Issue in the [I-ADOPT Examples Repository](https://github.com/mabablue/I-ADOPT-examples-playground/issues), add the link to the turtle, copy the graphic into the issue, and use the labels to describe with patterns you used

Find definitions of I-ADOPT in the [I-ADOPT ontology](https://i-adopt.github.io/ontology/) and some specific terms used in the design guide in this [glossary](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Guide/glossary.md). 

## 1. Step:
Analyse the variable description and, if necessary, rewrite it to provide a clear interpretation of the measured phenomenon. The help of a domain expert might be useful. Leave out details about the unit of measurements, the method and the instrument but make sure to include the property, the measured entity and the context defining the measurement. 

E.g. Atmospheric optical thickness of particulate organic matter at 550nm under ambient conditions.

-> Optical thickness of organic particle in aerosol in atmosphere at 550nm 
(ambient conditions is already captured in the term atmosphere). 

## 2. Step:
Segment the text into atomic parts based on meaning rather than syntax. Ensure that composite terms remain intact if further decomposition would result in a loss of specialized context. 

Compare: [Amospheric boundary layer height defined by temperture inversion](https://github.com/mabablue/I-ADOPT-examples-playground/issues/10) 

Decomposed: height; atmospheric boundary layer; defined by temperature inversion; 

## 3. Step
Determine the Property

Be as precise as possible and use a known physical quantity rather than a community convention to increase the clarity and reusability of the terms. In case the description uses a community convention use the physical quantity and add a *constraint: type* on it. 

Find one property pattern that applies for your variable using the decision trees.

**Decision trees:**
- [qualitative properties](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Decisition_trees/DT0.mmd)

In case it is a quantitative property with units and the units are known for the values, they can be useful for the recognition of the exact property addressed. [Here](https://i-adopt.github.io/terminologies/unit2property/) you can look up the property based on the unit. 
- [quantitative properties](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Decisition_trees/DT1.mmd)
- [derived properties](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Decisition_trees/DT2.mmd)
- [flux properties](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Decisition_trees/DT3.mmd)
- [ratio properties](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Decisition_trees/DT4.mmd)

## 4. Step
Determine the Object of Interest

Find one object of interest pattern that applies for your variable using the decision trees.

**Decision trees:**
- As shortcut: [Property vs Object of Interest vs Matrix](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Decisition_trees/DT6.mmd)
- [Object of Interest](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Decisition_trees/DT5.mmd)


## 5. Step
Determine the Matrix

Find one matrix pattern that applies for your variable using the decision trees.

**Decision trees:**
- As shortcut: [Property vs Object of Interest vs Matrix](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Decisition_trees/DT6.mmd)
- [Matrix](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Decisition_trees/DT7.mmd)

## 6. Step
Determine if the Statistical Modifiers are involved.

## 7. Step
Determine Constraints and place them under the correct component. Ensure each constraint is concise yet informative, and present only one distinct constraint per argument. A constraint must be type-labeld, following this naming convention [type:]constraint.

**Overview of patterns:**
-  [overview constraints](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Decisition_trees/Constraints_patterns.csv)

## 8. Step
Add Context Object, if necessary, to add clarity. Typical context objects are spheres like atmosphere, biosphere, or any additional information required despite the matrix.

