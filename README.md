# Conceptual Bot Platform
_A meta repository for the components of the conceptual bot platform_

The conceptual bot platform serves as a software system for modeling and analyzing conceptual RPA bots based on the ontology of RPA operations.
Furthermore, modeled conceptual RPA bots can be linked, i.e. translated, to existing RPA tools, currently [Robot Framework](https://robotframework.org/) and [taskt](http://www.taskt.net/).

You can find a demonstration of the platform here (TODO!).

## Available components
So far, the platform consists of a [front end (the modeler)](https://github.com/bptlab/conceptual-bot-modeler), and a [back end](https://github.com/bptlab/conceptual-bot-backend) for storing and linking bots.

### Conceptual RPA Bot Modeler
This modeler currently comprises the following functionality:
- Parsing the ontology of RPA operations
- Mapping from BPMO concepts to BPMN
- Modeling conceptual bots using the Business Process Model and Notation using operations from the ontology
- Support for different types of operations, such as triggers, decisions, and context containers
- Parsing BPMN models to generic process trees that are sent to the back end for storing
- Analzying stored bots for included operations and concepts, i.e. searching the bot repository for bots automating certain applications or using specific operations


### Conceptual RPA Bot Back End
The back end, serving as the bot repository, currently offers the following features:
- Storing the generic process tree and the visual BPMN representation of RPA bots
- Linking, i.e., translating, stored bots to either Robot Framework (`.robot`) or taskt files (`.xml`)
