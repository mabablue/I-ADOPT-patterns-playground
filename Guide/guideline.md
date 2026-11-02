# I-ADOPT Variable Design Guide


## Workflow:

1. Follow Variable Design Steps using Decision Trees (DT) leading to Variable Design Patterns (VDPs). Find here [instructions](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Guide/how-to-read-patterns.md) on how to interprete patterns. 
2. Use the **[I-ADOPT Visualizer](https://sirkos.github.io/iadopt-vis/)** to compose your variable.
3. Find appropriate semantic concepts from the vocabularies of your choice (or use this [lookup service](https://i-adopt.github.io/terminologies/list/all/)) and add their IRIs in the visualizer.
4. Copy RDF and safe it as turtle (.ttl) file in the [I-ADOPT Examples Repository](https://github.com/mabablue/I-ADOPT-examples-playground).
5. Create an Issue in the [I-ADOPT Examples Repository](https://github.com/mabablue/I-ADOPT-examples-playground/issues), add the link to the turtle, copy the graphic into the issue, and use the labels to describe with patterns you used.

Find definitions of I-ADOPT concepts and specific terms used here in this [glossary](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Guide/glossary.md). 

**Demo Example: [Ozone column molecular content](https://github.com/mabablue/I-ADOPT-examples-playground/blob/main/ECV/Atmosphere/Ozone.ttl)** - Definition: 2D field of total amount of O3 molecules per unit area in an atmospheric column extending from the Earth’s surface to the upper edge of the atmosphere.

## 1. Analyze
Analyse the variable description and, if necessary, rewrite it to provide a clear interpretation of the measured phenomenon. The help of a domain expert might be useful. Leave out details about the unit of measurements, the method and the instrument but make sure to include the property, the measured entity and the context defining the measurement. 

Demo example interpretation: *Molecules per area of ozone in the atmosphere (measured from Earth's surface to the upper edge of the amosphere)*

## 2. Decompose
Segment the text into logical atomic parts based on meaning rather than syntax. Ensure that composite terms remain intact if further decomposition would result in a loss of specialized context. 

Demo example decomposition: *molecules per area; ozone; atmosphere; measured from Earth's surface to the upper edge of the amosphere;*

## 3. Property

Be as precise as possible. Use a known physical quantity rather than a community convention to increase the clarity and reusability of the terms. In case the description uses a community convention use the physical quantity. Later (at step 7) add a *constraint: type* on it. 

Find one <code>Property</code> pattern that applies to your variable using the decision trees.

**Decision trees:**
- [qualitative properties](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Decision_trees/DT0.mmd)

In case it is a quantitative property with units and the units are known for the values, they can be useful for the recognition of the exact property addressed. [Here](https://i-adopt.github.io/terminologies/unit2property/) you can look up the property based on the unit. 
- [quantitative properties](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Decision_trees/DT2.mmd)
- [derived properties](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Decision_trees/DT3.mmd)
- [flux properties](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Decision_trees/DT4.mmd)
- [ratio properties](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Decision_trees/DT5.mmd)

Demo example <code>Property</code> pattern:
*Are there units associated with the result values? yes (molecules/m2) -> quantitative property -> derived property -> ratio -> quantities of different types -> no time in the denominator -> denominator is area -> numerator is entity -> [AREAL NuMBER DENSITY VDP127](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/pattern/VDP127.yaml)* 

Click on the pattern description to find instruction in the design info (see [glossary](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Guide/glossary.md)).

<img width="180" height="66" alt="image" src="https://github.com/user-attachments/assets/78d014ea-40f5-49c4-8d07-f3f752b40be7" />





## 4. Object of Interest

Find one <code>Object of Interest</code> pattern that applies for your variable using the decision trees.

**Decision trees:**
- As shortcut (works for most variables) [Property vs Object of Interest vs Matrix](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Decision_trees/DT7.mmd)
- [Ratio Object of Interests](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Decision_trees/DT5.mmd) including also specialized cases
- [Complex Object of Interests](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Decision_trees/DT6.mmd) involving systems or more than one property in a variable

Demo example <code>Object of Interest</code> pattern: *[Ratio Object of Interests](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Decision_trees/DT5.mmd) -> Areal density -> [RATIO VDP127](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/pattern/VDP127.yaml) -> Asymmetric System (numerator: ozone / denominator: area)*

<img width="383" height="151" alt="image" src="https://github.com/user-attachments/assets/b9d1aba0-57c9-40a6-8454-8bf4c67a02d4" />



## 5. Matrix

Find one <code>Matrix</code> pattern that applies for your variable using the decision trees.

**Decision trees:**
- As shortcut: [Property vs Object of Interest vs Matrix](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Decision_trees/DT7.mmd)
- [Matrix](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Decision_trees/DT8.mmd)

Demo example <code>Matrix</code> pattern: *no material flow, no natural process, no reference area, no different embedding material, but a [natural container VDP37](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/pattern/VDP41.yaml) -> Simple Matrix* 

<img width="164" height="59" alt="image" src="https://github.com/user-attachments/assets/4b6a4dd5-8e48-4bec-ac16-5bbcc209d77f" />

## 6. Statistical Modifier
Determine if <code>Statistical Modifiers</code> (like mean, standard deviation, maximum) are involved. See for example maximum in [daily maximum hourly precipation rate](https://github.com/mabablue/I-ADOPT-examples-playground/issues/124). If a statistical modifier modifies a value's unit, it turns into the <code>Property</code> instead. 

Demo example: no statitistal modifier found

## 7. Constraint
Determine <code>Constraints</code> and place them under the correct component. Ensure each constraint is concise yet informative, and present only one distinct constraint per argument. A constraint must be type-labeld, following this naming convention [type:]constraint.

**Overview of constraint patterns:**
-  [constraints](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/main/Decision_trees/Constraint_patterns.csv)

Demo Example <code>Constraint</code>: The Variable specifies that the unit area is related to the total atmospheric column extending from the Earth's surface to the upper edge of the atmosphere. Thus we require a spatial constraint on the denominator of the object of interest. 


<img width="184" height="208" alt="image" src="https://github.com/user-attachments/assets/fbd28431-2dfb-4d28-8351-79dbe19e2f15" />



## 8. Context Object
Add <code>Context Object</code>, if necessary, to add clarity. Typical context objects are spheres like atmosphere, biosphere, or any additional information required despite the matrix. See for example sea in [eastward velocity of water current in the water body](https://github.com/mabablue/I-ADOPT-examples-playground/issues/37).

Demo example: no context object needed

##
Solution demo example: [turtle file](https://github.com/mabablue/I-ADOPT-examples-playground/blob/main/ECV/Atmosphere/Ozone.ttl)


<img width="830" height="531" alt="image" src="https://github.com/user-attachments/assets/ba7c6b70-8295-46cb-89d6-6ebc4afcc9f6" />





IRIs for concepts:
- areal number density: https://www.wikidata.org/data/Q108914965 
- ozone: http://vocab.nerc.ac.uk/collection/S27/current/CS003171/
- area: http://vocab.nerc.ac.uk/collection/S06/current/S0600146/
- atmosphere: http://vocab.nerc.ac.uk/collection/S21/current/S21S001/

## 9. Alternative Community Pattern
As the demo example is a recurring variable in Atmospheric Sciences, <code>Variable Community Patterns</code> can be used instead of the generic core decomposition to align directly with domain conventions and established vocabularies like CF Conventions.

<img width="829" height="377" alt="image" src="https://github.com/user-attachments/assets/83e1d4f2-b0fc-416e-a91e-0a24719a6c4d"/>

Here we use a domain-specific property: column molecular content, which incorporates two simplifications over the neutral pattern:

1. The constraint on the denominator (the vertical integration scope) is encapsulated directly within the domain property (column molecular content). However a constraint is still needed to specify if the total or the partial column is meant.
2. The focus shifts from an abstract mathematical system (substance per unit area) to the physical target substance itself. The <code>Object of Interest</code> resolves to the substance of interest (ozone, using [ODP33](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/addf99e99a37f1b09a74e31678efb23b9b92ee53/pattern/ODP33.md): Single Entity or a defined chemical mixture), while the surrounding physical column environment is explicitly captured as the *<code>Matrix</code> (MDP41: atmosphere).

### Mapping to Core Pattern

To maintain semantic interoperability across domains without losing atmospheric community semantics, this pattern is formally bridged back to the generic areal density pattern ([VDP127](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/addf99e99a37f1b09a74e31678efb23b9b92ee53/pattern/VDP127.md)) via [MR2](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/addf99e99a37f1b09a74e31678efb23b9b92ee53/mapping/MR2.md):

* [VCP127](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/ebf5cc6ebbab80fb432ea5701bd86cd614be1f7a/pattern/domain_patterns/VCP127.md) (Community): _Property: column molecular content + ObjectOfInterest: ozone + Matrix: atmospheric column_
* [VDP127](https://github.com/mabablue/I-ADOPT-patterns-playground/blob/ebf5cc6ebbab80fb432ea5701bd86cd614be1f7a/pattern/VDP127.md) (Generic Core): _Property: areal number density + ObjectOfInterest: ozone/area ratio system_ 
