# Conceptual Bot Platform
_A meta repository for the components of the conceptual bot platform_

The conceptual bot platform serves as a software system for modeling and analyzing conceptual RPA bots based on the ontology of RPA operations.
Furthermore, modeled conceptual RPA bots can be linked, i.e. translated, to existing RPA tools, currently [Robot Framework](https://robotframework.org/) and [taskt](https://github.com/saucepleez/taskt).


Demonstration of the modeling component, including data resources and variables:
![ontorpa-modeling with data](https://github.com/user-attachments/assets/cf3dcf5a-26f8-417f-a592-c959455920c8)



Screencast of the platform featuring the modeling (video does not show modeling of data added later) and translation components (https://youtu.be/Pq5FIS9KtqA):

[![Thumbnail to screencast](https://img.youtube.com/vi/Pq5FIS9KtqA/0.jpg)](https://www.youtube.com/watch?v=Pq5FIS9KtqA)

For illustrations of the newer components, see the respective modules for [abstraction](https://github.com/bptlab/onto-rpa-platform/blob/main/components/abstraction/README.md) and the [complexity metrics](https://github.com/bptlab/onto-rpa-platform/blob/main/components/metrics/README.md).

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
- Apply different [abstraction strategies](https://github.com/bptlab/onto-rpa-platform/blob/main/components/abstraction/README.md) to models and view the result
- Automatically compute various [complexity metrics](https://github.com/bptlab/onto-rpa-platform/blob/main/components/metrics/README.md) for models


### Conceptual RPA Bot Back End
The back end, serving as the bot repository, currently offers the following features:
- Storing the generic process tree and the visual BPMN representation of RPA bots
- Linking, i.e., translating, stored bots to either Robot Framework (`.robot`) or taskt files (`.xml`)


## Installation
Requirements:
- node.js
- Docker or directly MongoDB

1. You need to clone/download the sources for the [back end](https://github.com/bptlab/conceptual-bot-backend) and the [front end](https://github.com/bptlab/conceptual-bot-modeler).
2. Run `npm install` in each directory (BE+FE)
3. Make sure you have MongoDB running at port `27017`.
4. Run `npm run dev` in each directory (BE+FE)
