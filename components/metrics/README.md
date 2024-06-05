_This is the readme for the metrics component. [See here for main readme of the OntoRPA platform.](https://github.com/bptlab/onto-rpa-platform)_

# Complexity Metrics for RPA Bot Models
The metrics component is implemented as a part of the [OntoRPA front end](https://github.com/bptlab/onto-rpa-frontend/).

It allows measuring various complexity metrics for models concerning operations, control flow, data flow and data resources.
Furthermore, the component computes the adapted Halstead-based Process Complexity metrics and the control-flow complexity.

![Screenshot of bot model with computed metrics](figures/OntoRPA-Metrics%20Example.png)

## Usage

![animation for opening the metrics view](figures/OntoRPA-Metrics%20Start.gif)
The new metrics view can be opened by clicking the respective icon on a bot model card.
All available metrics are automatically computed and the results are displayed next to the model itself.


![animation showing metrics view](figures/OntoRPA-Metrics%20Overview.gif)
For each metric, a brief explanation can be viewed.
Values with more then two decimal places are rounded, indicated by a tilde (~).
The actual value can be viewed by hovering over the value.


## Current Limitations

- The metrics implemented so far are not control-flow sensitive and thus might produce inacurrate numbers for models with decision logic.
- The user interface and presentation of the metrics need improvement, so far it's only a long list.
