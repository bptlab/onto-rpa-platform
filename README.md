_This is the readme for the abstraction component. [See here for main readme of the OntoRPA platform.](https://github.com/bptlab/onto-rpa-platform)_

# Abstraction of RPA Bot Models
The abstraction component is implemented as part of the [OntoRPA front end](https://github.com/bptlab/onto-rpa-frontend/).

![animation for opening abstraction view](figures/RPA_Onto-Abstraction%20Start.gif)
It offers two sliders controlling the dimensions of coverage and granularity.

---

![animation for coverage](figures/RPA_Onto-Abstraction%20Coverage.gif)
Using the coverage slider, the degree of elimination can be determined.
The elimination is based on weights assigned to classes in the operations-taxonomy as part of the ontology of RPA operations.

---

![animation for granularity](figures/RPA_Onto-Abstraction%20Granularity.gif)
Using the granularity slider, the level of aggregation can be determined.
With each slider step, more nodes that are intended for aggregation, are merged, resulting in a higher level of abstraction.
Nodes that are aggregated or intended for aggregation show their software context and data context in the label (see limitation below).
In this example, full coverage is chosen, thus not all nodes shown here are intended for aggregation, "blocking" some parts of the aggregation.

---

![animation for coverage and granularity](figures/RPA_Onto-Abstraction%20CovGran.gif)
Using both sliders in combination, a very abstract view can be obtained.
With the last slider step, also nodes across data contexts are aggregated.


## Current Limitations/Bugs
- Data context is only marked by random strings as the OntoRPA platform does not support the configuration of operations so far.
- When aggregating across data context, still the name of the first data context is used for label generation.
- No "speaking" names for high level operations included. The abstraction view here does use the ids instead of descriptive labels.
