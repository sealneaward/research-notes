# [Comparative Analysis of Prominent Middleware Platforms in theDomain of Ambient Assisted Living (AAL) for an Older Adults with Dementia (OAwD) Scenario](http://ac.els-cdn.com/S187705091630285X/1-s2.0-S187705091630285X-main.pdf?_tid=6ef3923a-ee5e-11e6-b06a-00000aab0f6b&acdnat=1486600183_6f0ebf218cebf08169be0d3c9368eb2a)

### General Ideas Taken From Article

- Pervasive computing has allowed for multiple components to communicate with each other through a shared middle ware platform.

- Customized Ambient Assisted Living platforms are customized pervasive systems that require extended evaluation methods, especially feature focused testing methods.

- Some examples of AAL are cognitive orthotics, home emergency detection, etc.

- The users of AAL are very diverse, in which a problem is presented in terms of customizing the system to fit every one person's needs.

- The paper provide a scenario of a person with dementia trying to make a cup of tea. The scenario consist of several steps that require completion before the scenario is complete. Each of the tasks have sensor to observe whether the person with dementia completes the task.

- Each of the sensors for the individual task produce an output to provide assistance to the user. These prompts are often given back to the user in audio form. When the system prompts the user, sensors continue to poll to see if the user has made the appropriate actions to complete the task.

- UniversAAL system provides communications though a bus architecture that follows a common publisher subscriber methodology.

# [An Ontology for Context-Aware Pervasive Computing Environments](http://ebiquity.umbc.edu/_file_directory_/papers/63.pdf)

### General Ideas Taken From Article

- The paper describes the COBRA ontology, which is a context-broker based system.
- The broker provides knowledge sharing, context reasoning, and privacy protections.

- An important part of pervasive development is having systems integrate agents that have knowledge and reasoning that allow them to be aware of the local context and share that knowledge withe other devices within the system.
- Context is defined to by information about location, environmental attributes, the people, devices, and objects that it contains.
- Ontologies are key for developing context-aware systems
- Several previous pervasive systems do little to support knowledge sharing and context reasoning.

### Context Broker Architecture

- A broker agent is critical to the architecture.
- The broker runs as a server that maintains a shared model of context for the rest of the agents within the system and to protect the privacy of users.
- All agents in a context-aware system are assumed to have prior knowledge to being a part of a context broker.

### Components of Context Broker

1. Context Knowledge Base: persistent storage of the context knowledge
2. Context Reasoning Engine: reactive interface engine that reasons over the stored context knowledge.
3. Context Aquisition Module: library of procedures that form a middle-ware abtraction for contexst aquisition.
4. Policy Managment Module: interence rules that deduce instructions for deciding the right permissions for differenrt computing entities to share information and management of agents receiving notification of context changes.

### Centralized Broker Pattern Negatives
- A centralized server creates a bottleneck effect, which is problematic in a large, scaled system.
- A solution proposed to the bottleneck is that of a fault-tolerance approach. This is where multiple brokers are grouped together to form a broker federation. Each broker in the federation manages a particular intelligent space. The federation is organized by a communication structure.

### COBRA-ONT
- COBRA-ONT is a collection of ontologies expressed in the Web Ontology Languae (OWL) that describe information in an intelligent meeting room envirnoment.
- OWL is used to model ontologies because it is much more expressive, which allows developers to contain more knowledge within the ontology.
- OWL was speicifically designed as an ontology lagnuage, where OWL has many predefiend classes and properties that are useful when sharing context knowledge.
- COBRA-ONT is split into four seperate ontology themes: physical places, agents, location context of agents, and activity context of agents.

### Place Ontologies
- The pysical place ontology class represents an abstraction of a physical location.
- The class contains properties that describe a location.
- The ontology has two sub-classes: AtomicPlace and CompoundPlace which both have distinctive containment properties.
- Containment properties are defiend as models that are capable of subsuming other physical locations. IE/ Campus subsumes all buildings on campus.
- Compound Places can only subsume places.

### Agent Ontologies

- The Agent class contains two subclasses: Person and SoftwareAgent
- Each class has properties that describe the agent as well as the agent's current role
- The agent's role can be represented as: Role, SpeakerRole, and AudienceRole
- The role property is used to characterize the intention of the agent.

### Location Ontologies

- Location ontology contains classes and properties that describes the location of an agent.
- The location class properties are similar to that of the Place ontology, where locations can either be Atomic or Compound.
- Instead of subsume location, agents follow the same rules. Atomic locations can only house one agent, where agents can be in multiple compound locations at the same time as long as the locations subsume eachother.

### Activity Ontology

- Activity Ontology is dynamic knowledge that describes the events that an agent participates in.
- Events are assumed to have schedules.
- THere is one main ontology class to represent the scheduled events: PresentationSchedule.
- The presentation class has proeprties that descrive; start time, end time, presentation title, presentation abstract, etc.
