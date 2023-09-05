_This is the readme for the abstraction component. [See here for main readme of the OntoRPA platform.](https://github.com/bptlab/onto-rpa-platform)_

# Abstraction of RPA Bot Models
The abstraction component is implemented as part of the [OntoRPA front end](https://github.com/bptlab/onto-rpa-frontend/).
Internally, it operates on process trees, which are created from the BPMN model.

![animation for opening abstraction view](figures/RPA_Onto-Abstraction%20Start.gif)
It offers two sliders controlling the dimensions of coverage and granularity.

---
## Coverage

![animation for coverage](figures/RPA_Onto-Abstraction%20Coverage.gif)
Using the coverage slider, the degree of elimination can be determined.
The elimination is based on weights assigned to classes in the operations-taxonomy as part of the ontology of RPA operations.
> Opening a new application is assigned a rather low weight, "BrowserOpen" and "ExcelOpen" are removed first, consequently.
> After that, opening a new URL in the browser followed by clicking a button in the browser is removed.

---
## Granularity

![animation for granularity](figures/RPA_Onto-Abstraction%20Granularity.gif)
Using the granularity slider, the level of aggregation can be determined.
With each slider step, more nodes that are intended for aggregation, are merged, resulting in a higher level of abstraction.
Nodes that are aggregated or intended for aggregation show their software context and data context in the label (see limitation below).
In this example, full coverage is chosen, thus not all nodes shown here are intended for aggregation, "blocking" some parts of the aggregation.
> With the first slider step, sequences of the same operation are aggregated, i.e., "BrowserGetText", "BrowserSelectItem", and "ExcelWriteCellValue".
> Subsequently, in the example, different operations that belong to the same "super-type" are aggregated, such as "BrowserGetText" and "BrowserGetAttribute" to "data-extraction-operation".
> Then, again operations with the same type at the next, more abstract level in the taxonomy are aggregated, such as "data-extraction-operation" and "data-input-operation" which both are "data-operations".

---
## Coverage & Granularity

![animation for coverage and granularity](figures/RPA_Onto-Abstraction%20CovGran.gif)
Using both sliders in combination, a very abstract view can be obtained.
With the last slider step, also nodes across data contexts are aggregated.
> In this example, aggregation is performed similar to the clip above.
> However, as other intermediate operations are removed, more operations can be aggregated.
> Eventually, with the last slider step, aggregation is performed across data context, as "data-operation" in data context 75 and "BrowserGetText" in data context 35 are aggregated to a joint "data-operation".

## Current Limitations/Bugs
- Data context is only marked by random strings as the OntoRPA platform does not support the configuration of operations so far.
- When aggregating across data context, still the name of the first data context is used for label generation.
- No "speaking" names for high level operations included. The abstraction view here does use the ids instead of descriptive labels.
