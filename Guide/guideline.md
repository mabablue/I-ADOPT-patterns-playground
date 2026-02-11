# I-ADOPT Variable Design Guide


## Workflow:

1. Follow Variable Design Steps using Decision Trees (DT) leading to Variable Design Patterns (VDPs).
2. Use the **[I-ADOPT Visualizer](https://sirkos.github.io/iadopt-vis/)** to compose your variable.
3. Find appropriate semantic concepts from the vocabularies of your choice (or use this [lookup service](https://i-adopt.github.io/terminologies/list/all/)) and add their IRIs in the visualizer.
4. Copy RDF and safe it as turtle (.ttl) file in the [I-ADOPT Examples Repository](https://github.com/mabablue/I-ADOPT-examples-playground).
5. Create an Issue in the [I-ADOPT Examples Repository](https://github.com/mabablue/I-ADOPT-examples-playground/issues), add the link to the turtle, copy the graphic into the issue, and use the labels to describe with patterns you used.

Find definitions of I-ADOPT concepts and specific terms used here in this [glossary](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Guide/glossary.md). 

**Demo Example: [Ozone total column](https://github.com/mabablue/I-ADOPT-examples-playground/blob/main/ECV/Atmosphere/Ozone.ttl)** - Definition: 2D field of total amount of O3 molecules per unit area in an atmospheric column extending from the Earth’s surface to the upper edge of the atmosphere.

## 1. Analyze
Analyse the variable description and, if necessary, rewrite it to provide a clear interpretation of the measured phenomenon. The help of a domain expert might be useful. Leave out details about the unit of measurements, the method and the instrument but make sure to include the property, the measured entity and the context defining the measurement. 

Demo example interpretation: *Mole per area of ozone in the atmosphere (measured from Earth's surface to the upper edge of the amosphere)*

## 2. Decompose
Segment the text into atomic parts based on meaning rather than syntax. Ensure that composite terms remain intact if further decomposition would result in a loss of specialized context. 

Demo example decomposition: *mole per area; ozone; atmosphere; measured from Earth's surface to the upper edge of the amosphere;*

## 3. Property

Be as precise as possible. Use a known physical quantity rather than a community convention to increase the clarity and reusability of the terms. In case the description uses a community convention use the physical quantity and add a *constraint: type* on it (see step 7). 

Find one <code>Property</code> pattern that applies to your variable using the decision trees.

**Decision trees:**
- [qualitative properties](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Decisition_trees/DT0.mmd)

In case it is a quantitative property with units and the units are known for the values, they can be useful for the recognition of the exact property addressed. [Here](https://i-adopt.github.io/terminologies/unit2property/) you can look up the property based on the unit. 
- [quantitative properties](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Decisition_trees/DT1.mmd)
- [derived properties](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Decisition_trees/DT2.mmd)
- [flux properties](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Decisition_trees/DT3.mmd)
- [ratio properties](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Decisition_trees/DT4.mmd)

Demo example <code>Property</code> pattern:
*Are there units associated with the result values? yes (mol/m2) -> quantitative property -> derived property -> ratio -> quantities of different types -> no time in the denominator -> mixture in a system -> denominator needed -> [density VDP14](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/pattern/VDP14.yaml)* 
<img width="164" height="57" alt="image" src="https://github.com/user-attachments/assets/8631fc12-1d6c-4352-8f14-fbf0f9cdb0a5" />


## 4. Object of Interest

Find one <code>Object of Interest</code> pattern that applies for your variable using the decision trees.

**Decision trees:**
- As shortcut: [Property vs Object of Interest vs Matrix](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Decisition_trees/DT6.mmd)
- [Object of Interest](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Decisition_trees/DT5.mmd)

Demo example <code>Object of Interest</code> pattern: *[shortcut](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Decisition_trees/DT6.mmd) -> Density -> [Ratio VDP26](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/pattern/VDP26.yaml) -> Asymmetric System (numerator: ozone / denominator: ground surface)*
<img width="354" height="142" alt="image" src="https://github.com/user-attachments/assets/4fee90d1-638f-4094-89b1-83bfacb17793" />


## 5. Matrix

Find one <code>Matrix</code> pattern that applies for your variable using the decision trees.

**Decision trees:**
- As shortcut: [Property vs Object of Interest vs Matrix](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Decisition_trees/DT6.mmd)
- [Matrix](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Decisition_trees/DT7.mmd)

Demo example <code>Matrix</code> pattern: *no material flow, no natural process, no reference area, no different embedding material, but a [natural container VDP37](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/pattern/VDP37.yaml) -> Simple Matrix* 

<img width="164" height="59" alt="image" src="https://github.com/user-attachments/assets/4b6a4dd5-8e48-4bec-ac16-5bbcc209d77f" />

## 6. Statistical Modifier
Determine if <code>Statistical Modifiers</code> (like mean, standard deviation, maximum) are involved. See for example maximum in [daily maximum hourly precipation rate](https://github.com/mabablue/I-ADOPT-examples-playground/issues/124). If a statistical modifier modifies a value's unit, it turns into the <code>Property</code> instead. 

Demo example: no statitistal modifier found

## 7. Constraint
Determine <code>Constraints</code> and place them under the correct component. Ensure each constraint is concise yet informative, and present only one distinct constraint per argument. A constraint must be type-labeld, following this naming convention [type:]constraint.

**Overview of constraint patterns:**
-  [constraints](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Decisition_trees/Constraints_patterns.csv)

Example <code>Constraint</code> pattern:  Context -> [defining entity VDP85](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/pattern/VDP85.yaml) on the <code>Property</code>

<img width="163" height="188" alt="image" src="https://github.com/user-attachments/assets/469ad8c9-d6c7-4852-a7ef-4accea4f71a7" />


## 8. Context Object
Add <code>Context Object</code>, if necessary, to add clarity. Typical context objects are spheres like atmosphere, biosphere, or any additional information required despite the matrix. See for example sea in [eastward velocity of water current in the water body](https://github.com/mabablue/I-ADOPT-examples-playground/issues/37).

Demo example: no context object needed

##
Solution demo example: [turtle file](https://github.com/mabablue/I-ADOPT-examples-playground/blob/main/ECV/Atmosphere/Ozone.ttl)

<img width="754" height="385" alt="image" src="https://github.com/user-attachments/assets/03e011e4-dbf5-4746-baa2-fa98d8c82536" />


IRIs for concepts:
- ozone: http://vocab.nerc.ac.uk/collection/S27/current/CS003171/
- ground surface: http://vocab.nerc.ac.uk/collection/S20/current/S2000011/
- atmosphere: http://vocab.nerc.ac.uk/collection/S21/current/S21S001/


