# Requirements Engineering

- The process of establishing the services that a customer requires from a system and the constraints under which it operates and is developed.
- The system requirements are the descriptions of the system services and constraints that are generated during the requirements engineering process.
---
### What is a Requirement?

- It may range from a high-level abstract statement of a service or of a system constraint to a detailed mathematical functional specification.
- This is inevitable as requirements may serve a dual function
	- May be the basis for a bid for a contract - therefore must be open to interpretation; 
	- May be the basis for the contract itself - therefore must be defined in detail;
	- Both these statements may be called requirements.

---
### Requirements Abstraction

If a company wishes to let a contract for a large software development project, it must define its needs in a sufficiently abstract way that a solution is not pre-defined. The requirements must be written so that several contractors can bid for the contract, offering, perhaps, different ways of meeting the client organization's needs. Once a contract has been awarded, the contractor must write a system definition for the client in more detail so that the client understands and can validate what the software will do. Both of these documents may be called the requirements document for the system.

---
### Types of Requirement

User requirements
- Statements in natural language plus diagrams of the services the system provides and its operational constraints. Written for customers.
System requirements
- A structured document setting out detailed descriptions of the system's functions, services and operational constraints. Defines what should be implemented so may be part of a contract between client and contractor.

---
### Reader of Different Types of Requirements Specification

![[{A054DD3F-DF9C-46FF-8B7D-3DB90E1DEB79}.png]]

---
### System Stakeholders

- Any person or organization who is affected by the system in some way and so has a legitimate interest.
- Stakeholder types
	- End users
	- System managers
	- System owners
	- External Stakeholders

---
### Agile Methods and Requirements

- Many agile methods argue that producing detailed system requirements is a waste of time as requirements change so quickly.
- The requirements document is therefore always out of date.
- Agile methods usually use incremental requirements engineering and may express requirements as 'user stories'.
- This is practical for business systems but problematic for systems that require pre-delivery analysis (e.g. critical systems) or systems developed by several teams.

---
### Functional and Non-Functional Requirements

Functional requirements
- Statements of services the system should provide, how the system should react to particular inputs and how the system should behave in particular situations.
- May state what the system should not do.
Non-functional requirements
- Constraints on the services or functions offered by the system such as timing constraints, constraints on the development process, standards, etc.
- Often apply to the system as a whole rather than individual features or services.
Domain requirements
- Constraints on the system from the domain of operation

---
### Functional Requirements
 
- Describe functionality or system services.
- Depend on the type of software, expected users and the type of system where the software is used.
- Functional user requirements may be high-level statements of what the system should do.
- Functional system requirements should describe the system services in detail.

---
### Requirements Imprecision

- Problems arise when functional requirements are not precisely stated.
- Ambiguous requirements may be interpreted in different ways by developers and users.
Consider the term 'search' in requirement 1
- User intention - search for a patient name across all appointments in all clinics;
- Developer interpretation - search for a patient name in an individual clinic. User chooses clinic then search.

---
### Requirements Completeness and Consistency

- In principle, requirements should be both complete and consistent.
- Complete
	- They should include descriptions of all facilities required.
- Consistent
	- There should be no conflicts or contradictions in the descriptions of the system facilities.
- In practice, because of system and environmental complexity, it is impossible to produce a complete and consistent requirements document.

---
### Non-Functional Requirements

- These define system properties and constraints e.g. reliability, response time and storage requirements. Constraints are 1/0 device capability, system representations, etc.
- Process requirements may also be specified mandating a particular IDE, programming language or development method.
- Non-functional requirements may be more critical than functional requirements. If these are not met, the system may be useless.

### Non-Functional Requirements Implementation

- Non-functional requirements may affect the overall architecture of a system rather than the individual components.
	- For example, to ensure that performance requirements are met, you may have to organize the system to minimize communications between components.
- A single non-functional requirement, such as a security requirement, may generate a number of related functional requirements that define system services that are required.
	- It may also generate requirements that restrict existing requirements.

### Types of Nonfunctional Requirement

![[{F6D634E5-A4E9-4D6A-B463-C17889555F24}.png]]


---
### Non-Functional Classifications

Product requirements
- Requirements which specify that the delivered product must behave in a particular way e.g. execution speed, reliability, etc.
Organizational requirements
- Requirements which are a consequence of organizational policies and procedures e.g. process standards used, implementation requirements, etc.
External requirements
- Requirements which arise from factors which are external to the system and its development process e.g. interoperability requirements, legislative requirements, etc.

---
### Goals and Requirements

- Non-functional requirements may be very difficult to state precisely and imprecise requirements may be difficult to verify.
- Goal 
	- A general intention of the user such as ease of use.
- Verifiable non-functional requirement
	- A statement using some measure that can be objectively tested.
- Goals are helpful to developers as they convey the intentions of the system users.

---
### Usability Requirements

- The system should be easy to use by medical staff and should be organized in such a way that user errors are minimized. (Goal)
- Medical staff shall be able to use all the system functions after four hours of training. After this training, the average number of errors made by experienced users shall not exceed two per hour of system use. (Testable non- functional requirement)

---
### Metrics for Specifying Nonfunctional Requirements

![[{BF596A2C-FF01-4376-AD6D-CBCF300E348F}.png]]

---
### Requirements Engineering Processes

- The processes used for RE vary widely depending on the application domain, the people involved and the organization developing the requirements.
- However, there are a number of generic activities common to all processes
	- Requirements elicitation;
	- Requirements analysis;
	- Requirements validation;
	- Requirements management.
- In practice, RE is an iterative activity in which these processes are interleaved.

---
### A Spiral View of the Requirements Engineering Process

![[{4D7D99D9-B139-48F5-8F23-F5B946BA77FE}.png]]

---
### Requirements Elicitation and Analysis

- Sometimes called requirements elicitation or requirements discovery.
- Involves technical staff working with customers to find out about the application domain, the services that the system should provide and the system's operational constraints.
- May involve end-users, managers, engineers involved in maintenance, domain experts, trade unions, etc. These are called stakeholders.

---
### Requirements Elicitation

- Software engineers work with a range of system stakeholders to find out about the application domain, the services that the system should provide, the required system performance, hardware constraints, other systems, etc.
- Stages include:
	- Requirements discovery,
	- Requirements classification and organization,
	- Requirements prioritization and negotiation,
	- Requirements specification.

---
### Problems of Requirements Elicitation

- Stakeholders don't know what they really want.
- Stakeholders express requirements in their own terms.
- Different stakeholders may have conflicting requirements.
- Organizational and political factors may influence the system requirements.
- The requirements change during the analysis process. New stakeholders may emerge and the business environment may change.

---
### The Requirements Elicitation and Analysis Process

![[{D39F3F34-1FCD-4BD3-AE5A-DDA47C44273B}.png]]

---
### Process Activities

Requirements discovery
- Interacting with stakeholders to discover their requirements. Domain requirements are also discovered at this stage.
Requirements classification and organization
- Groups related requirements and organizes them into coherent clusters.
Prioritization and negotiation
- Prioritizing requirements and resolving requirements conflicts.
Requirements specification
- Requirements are documented and input into the next round of the spiral.

---
### Requirements Discovery

- The process of gathering information about the required and existing systems and distilling the user and system requirements from this information.
- Interaction is with system stakeholders from managers to external regulators.
- Systems normally have a range of stakeholders.

---
### Interviewing 

- Formal or informal interviews with stakeholders are part of most RE processes.
- Types of interview
	- Closed interviews based on pre-determined list of questions
	- Open interviews where various issues are explored with stakeholders.
- Effective interviewing
	- Be open-minded, avoid pre-conceived ideas about the requirements and are willing to listen to stakeholders.
	- Prompt the interviewee to get discussions going using a springboard question, a requirements proposal, or by working together on a prototype system.

---
### Problems with Interviews

- Application specialists may use language to describe their work that isn't easy for the requirements engineer to understand.
- Interviews are not good for understanding domain
	- Requirements engineers cannot understand specific domain terminology;
	- Some domain knowledge is so familiar that people find it hard to articulate or think that it isn't worth articulating.

---
### Ethnography

- A social scientist spends a considerable time observing and analyzing how people actually work.
- People do not have to explain or articulate their work.
- Social and organizational factors of importance may be observed.
- Ethnographic studies have shown that work is usually richer and more complex than suggested by simple system models.

---
### Scope of Ethnography

- Requirements that are derived from the way that people actually work rather than the way I which process definitions suggest that they ought to work.
- Requirements that are derived from cooperation and awareness of other people's activities.
	- Awareness of what other people are doing leads to changes in the ways in which we do things.
- Ethnography is effective for understanding existing processes but cannot identify new features that should be added to a system.

---
### Ethnography and Prototyping for Requirements Analysis

![[{D535EFAC-B09A-477E-A4E1-5DABD6F7270B}.png]]

---
### Stories and Scenarios

- Scenarios and user stories are real-life examples of how a system can be used.
- Stories and scenarios are a description of how a system may be used for a particular task.
- Because they are based on a practical situation, stakeholders can relate to them and can comment on their situation with respect to the story.

---
### Scenarios

- A structured form of user story
- Scenarios should include
	- A description of the starting situation;
	- A description of the normal flow of events;
	- A description of what can go wrong;
	- Information about other concurrent activities;
	- A description of the state when the scenario finishes.

---
### Requirements Specification

- The process of writing down the user and system requirements in a requirements document.
- User requirements have to be understandable by end- users and customers who do not have a technical background.
- System requirements are more detailed requirements and may include more technical information. 
- The requirements may be part of a contract for the system development
	- It is therefore important that these are as complete as possible.

---
### Ways of Writing a System Requirements Specification

![[{96F76191-F22A-43F6-AE32-45A837B3E311}.png]]

---
### Requirements and Design

- In principle, requirements should state what the system should do and the design should describe how it does this.
- In practice, requirements and design are inseparable
	- A system architecture may be designed to structure the requirements;
	- The system may inter-operate with other systems that generate design requirements;
	- The use of a specific architecture to satisfy non-functional requirements may be a domain requirement.
	- This may be the consequence of a regulatory requirement.

---
### Natural Language Specification

- Requirements are written as natural language sentences supplemented by diagrams and tables.
- Used for writing requirements because it is expressive, intuitive and universal. This means that the requirements can be understood by users and customers.

---
### Guidelines for Writing Requirements

- Invent a standard format and use it for all requirements.
- Use language in a consistent way. Use shall for mandatory requirements, should for desirable requirements.
- Use text highlighting to identify key parts of the requirement.
- Avoid the use of computer jargon.
- Include an explanation (rationale) of why a requirement is necessary.

---
### Problems with Natural Language

Lack of clarity
- Precision is difficult without making the document difficult to read.
Requirements confusion
- Functional and non-functional requirements tend to be mixed-up.
Requirements amalgamation
- Several different requirements may be expressed together.

---
### Structured Specifications

- An approach to writing requirements where the freedom of the requirements writer is limited and requirements are written in a standard way.
- This works well for some types of requirements e.g. requirements for embedded control system but is sometimes too rigid for writing business system requirements.

---
### Form-Based Specifications

- Definition of the function or entity.
- Description of inputs and where they come from.
- Description of outputs and where they go to.
- Information about the information needed for the computation and other entities used.
- Description of the action to be taken.
- Pre and post conditions (if appropriate).
- The side effects (if any) of the function.

---
### Tabular Specification

- Used to supplement natural language.
- Particularly useful when you have to define a number of possible alternative courses of action.
- For example, the insulin pump systems bases its computations on the rate of change of blood sugar level and the tabular specification explains how to calculate the insulin requirement for different scenarios.

---
### Use Cases

- Use-cases are a kind of scenario that are included in the UML.
- Use cases identify the actors in an interaction and which describe the interaction itself.
- A set of use cases should describe all possible interactions with the system.
- High-level graphical model supplemented by more detailed tabular description.
- UML sequence diagrams may be used to add detail to use-cases by showing the sequence of event processing in the system.

---
