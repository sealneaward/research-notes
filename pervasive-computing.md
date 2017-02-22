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

# [Developing Context-Aware Pervasive Computing Applications: Models and Approach](http://citeseerx.ist.psu.edu/viewdoc/download;jsessionid=C2D753E13FBCB55712C97EED1AACB5FA?doi=10.1.1.59.8031&rep=rep1&type=pdf)

### General Ideas Taken From Paper

- Pervasive systems require ability to operate in highly dynamic environments without intervention by users. Context aware systems aim to meet these requirements by adapting to the current location, time, and user activities.

- There have been many models that have been developed in the research community for context-aware use, but most have not left the lab. This is largely because of the overhead of development cost, concerns about privacy and security, and a misunderstanding of context-awareness.

The paper is divided into two major sections to solve the three problems listed above:

1. Simpifying Design and Implementation Tasks
2. Rapid Prototyping and Experimentation

### Context Modelling Approach

- Context-aware development has largely been focused on infrastructure development to incorporate that gathering, managing, and interpreting context information. Current measures encourage reusability of functionality and simplification of application development, which can lead to too much abstraction for context descriptions.

##### Characteristics of Context Information

- Previous context models oonly derived information from sensors. The model proposed takes information from sensors, static information, and user-supply side. The model then determines which information is the most pertanent to the situation at hand.

- Different information sources have different degress of reliability. Information from sensors is very dynamic and can contain lots of noise, where user supplied information is very reliable, but can become outdated.

##### Graphical Modelling Approach

- The Context Modelling Language is developed as a tool to assist designers when exploring and specifying context requirements.
-  Provides modelling constructs for truth of information, the different classification and the information, useful metadata, and dependences among different information types.
- CML was formed as an extension to Object-Role modelling (ORM)
- ORM was used as a base line for construction of CML becase of the formalities and the closeness to the modelling approach.

CML Captures:

1. User activities that covers past, present, and future activities.
2. Associations between users and communications device.
3. Locations of users and devices.

###### Relational Representation

- Relational mapping creates a representation of CML fact types that help with context management tasks: enforcement of constraints, storage within a database, amd querying the applications.
- The relational mapping can be represented in a database.

###### Situation Asbtraction

- The graphical model notation works when specifying the context infromation used by a context-awar application, and its relational mapping stored context, but neither serve as an abstraction for programming.
- Situation abstraction is a way to define conditions of the context in terms of the fact abstraction.
- Situations can be combined, promoting reuse and incremental combinations by the programmer.

### Preference Model

- Tools are used to to support the decision making proceess involved in mapping the context to application behaviours.
- Explicit means to represent user preferecnce is required in context modelling.
The preference model presented supports the ranking of chouces according to the context. Communication application allows the choices to be the communication channels that are used by people to talk to each other.
- Each preference task the form of a pair consisting of a scope and a scoring function. The score represents a choice to be made.
- Preferences can be grouped into sets and be combined according to policies.

### Programming models

- Context aware programming has been developed using traditional methods where the context logic is often hard coded into the system. The source code must be edited to support additional behaviours and contexts.

###### Branching

- The branching model is designed to assist in decision problems involved in a context-dependent choive among a set of alternatives. In information retrieval, branching can be sued to select relevant information to present to the user, as well as the most suitable form of presentation. This approach results in the tight binding of the context model to the application logic, making it harder to evolve.
-  To solve this problem, the preference model is leveraged. User preferences act as the link between the context and the preferred action. Preferences assign ratings to the alternatices according to the context.


###### Triggering

- A trigger mechanism is employed to support actions that are invoked due to context changes. These context changes are listed as true, false, and possibly true. Triggers are associated with changes of context state.

### Software Infrastructure

- The infrastructure of context-aware systems are comprised of loosely coupled layers. The context-gathering layer aquires context from sensors and process the information to create a level of abstraction for the context management system. To connect to the management system, there exists a content-based routing mechanism.
- The context management layer maintains a set of context models in terms of the their relationship representations.
- There exists a query layer to provide applications access to the context management system.
- The adaptation layer manages repositories of situations, as well as trigger and preference definitions.
- The application layer provides tookit support for the programming models.

### Case Study

- The authors of the paper carried out a case study where they built a context-aware communication tool. The study compared different models to show how well each faired in maintanability, being easy to add new features, and reusability for context definitions and context processing.

# [Providing Contextual Information to Pervasive Computing Applications](http://www.cs.cmu.edu/~aura/docdir/Percom03.pdf)

### General Ideas Taken From Paper

- The authors introduce the Contextual Information Service (CIS). ICS provides applications with contextual information from a virtual database.
- The CSI provides contextual information around the location of people, the location and properties of printers, the amount of bantwidth available, etc. The information on different devices is provided through Contextual Information Providers that operate within a virtual database.
- In different scenarios, the effort behind developing context-aware applications is difficult and can render function non-reusable. This is an ineffecient way of development, as many situation that require context would require additional code to be written. A solution to this problem is storing context information inside of a database.
- The limations to storing raw contextual informamtion in a database is that database are static and require large amounts of cotnext-gathering before hand, Contextual information also has metadata assoaciated with it: accuracy and freshnesss, which cannot be stored in a traditional database correctly.
- To address the limitations of a traditional database, CIS uses a virtual database. The virtual database provides contexual information through a query interface. The information is stored and managed by a set of ditributed contextual information providers.

### CIS Design Requirements

##### Clients can Easily Synthesize Required Contextual Information

- CIS should provide contextual information while requiring minimal effort from the client. This can be done be allowing clients to retreive information from contextual providers. Ontop of providers access, CIS supports callback functions that reduce the need for polling at the client level.

##### Effecient Information Providers

- Contextual information is usually static, which makes easy storage in a database and easy for provider support.
- Contextual information can also be dynamic, which cannot be stored in a static database. Dynamic information does not work in a static database. Providers support dynamic information as they compute the results as requests come in, giving up to date contextual information. The information required should be of the lower accuracy, due to the dynamic nature of the information being requested.

##### Dynamic Attributes

- Dynamic information comes at lower certainty than static information. IE/ The location of a person can change (uncertain) where the name of a person does not usually change(certain).
- To support this information, clients must be able to query the contextual information in a query and the clients must be able to specify attributes of the meta data.
- The meta data to be supported is:

1. Accuracy
2. Confidence
3. Update Time
4. Sample Interval

### System Architecture

##### Contextual Information Service Architecture

1. Client issues query using the Contextual Service Interface
2. Queries are composed by the Query Synthesizer and sent to providers

- This approach enables clients to focus on the information that they desire.
- It also allows contextual information providers to be implemented without sacrificing basic functionality.

##### Contextual Information Provider Classes

- Providing information on the aspects of contextual environment can be done by providing information on entities and relationships that can be grouped into a small number of classes.
- The entities tracked are: peopel, devices, physical spaces, and networks. The main example of tracking people and paper printers, context providers will need to be created for each.
- Network classes are used to facilitate communication between applications providers.
