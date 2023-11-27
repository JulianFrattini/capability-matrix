# Context Specification

_The context specification defines the context of the Capability Matrix System including a specification of the overall project scope, the stakeholders, rules, goals, and constraints as well as a specification of the domain model._

## Project Scope

_Problem description and a statement of intent, i.e. a conclusion of the objectives of a potentially resulting project._

Problem Descriptions: A research group is defined by the capabilities of its individual members. Making these capabilities explicit allows the group to identify opportunities to collaborate in research applications, strategically expand its capabilities by recruitment efforts, and visualize individual and cluster-wise capabilities. The following challenges are considered in scope of this project:

1. Understanding of capabilities: Capabilities are hard to grasp, systematically elicit, and distinguish.
2. Recording capabilities: Specifying which capabilities a researcher has to which degree is tedious.
3. Maintaining capabilities: Keeping capabilities and the extent to which they are obtained up-to-date is impossible without a framework.
4. Communicating capabilities: It is difficult to visualize the capability profile (1) of a single researcher as well as (2) of a research group.

Statement of Intent: A system that both helps to undestand and frame capabilities of a specific research domain (e.g., requirements engineering), but also assists recording, maintaining, and communicating these abilities to external stakeholders and potential collaborators.

## Stakeholder Model

_Stakeholders comprehend individuals, groups, or institutions having the responsibility for requirements and a major interest in the project. User groups are a specialisation of  stakeholders interacting with the system._

```mermaid
classDiagram
    class Researcher {
        +leading: boolean
        +internal: boolean
        +applyForFunding(): void
    }

    class Institution {
        +areas: list[enum]
    }

    class FundingAgency {
        +interest: list[enum]
        +publishCall(): void
        +decideFundingApplication(): boolean
    }

    class Practitioner {
        +champion: boolean
        +lookingForOffering(): Researcher
        +checkUpOnResearcher(): CompanyCard
    }

    class Student {
        +lookingForSupervisor(): Researcher
    }

    Researcher --o Institution
    Researcher --> FundingAgency
    Student --> Researcher
    Practitioner --> Researcher
```

## Objectives and Goals 

_Each goal, whether it is a business goal, a usage goal, or a system goal, is issued by a stakeholder. Goals satisfy the statement of intent, they build a hierarchy, and they can influence each other in terms of conflicts, constraints, or support._

| ID | Stakeholder | Goal | Type |
|---|---|---|---|
| G1 | Researcher | Getting an overview of the capabilities of a research group to assess their capability distribution and maturity | Usage |
| G2 | Lead researcher | Identifying lack of capabilities in a research group for targeted hiring | Usage |
| G3 | Researcher | Keeping capability records up-to-date | System |
| G4 | Researcher | Identifying collaborators with specific capabilities to answer a funding call | Usage |
| G5 | Researcher | Visualizing a personal capability portfolio (e.g., to a funding agency) | Business |
| G6 | Institution | Visualizing success of own research groups | Business |
| G7 | Funding Agency | Assessing the academic profile of a researcher | Usage |
| G8 | Student | Finding an eligible supervisor for a thesis | Usage |
| G9 | Practitioner | Finding an eligible researcher for a collaboration | Usage |
| G10 | Practitioner | Follow the activities of a researcher | Usage |
| G11 | Researcher | Prioritizing the visualization of problem-oriented over solution-oriented capabilities | Usage |
| G12 | Researcher | Highlighting select capabilities in their profile | Usage |

G11 was introduced to maintain control over the practitioners' expectations: when presenting solution-oriented capabilities (technical capabilities like AI/ML, tool development, NLP, etc.) too prominently, practitioners may be eager to employ a researcher to develop a solution rather than inviting them to investigate the problem.

## Domain Model

_The external systems, that interact with the system under development, compose the domain model. For business information systems, the domain model is extended with a business process model represented in various types of activities that need and produce business objects. A business process model is a collection of all instances of the activities and their (causal) relations._

### Static Domain Model

The static domain model describes the entities relevant to the context of the system and their relationship among each other.

```mermaid
classDiagram
    direction TB

    class CapabilityGroup {
        +name: str
        +importance: int
    }

    class Capability {
        +name: str
        +definition: str
    }

    class Evidence {
        +name: str
        +date: date
    }

    class Publication {
        +venue: str
        +authorship: int
    }

    class Repository {
        +location: url
        +license: enum
    }

    class Certificate {
        +issuer: str
    }

    Capability "1..*" --> "1..*" Evidence : is proven by
    Capability "1" --> "0..*" Capability : decomposes into
    CapabilityGroup "1" *-- "1..*" Capability : is composed of

    Repository --|> Evidence
    Publication --|> Evidence
    Certificate --|> Evidence
```

### Dynamic Domain Model

The dynamic domain model visualizes the business processes as implied by the goals.

**G1: Obtaining an Overview**

```mermaid
sequenceDiagram
participant Researcher
participant Research Group Representative
participant Member 1
participant Member n
Researcher ->> Research Group Representative: Request Overview 
Research Group Representative ->> Member 1: Request Capability Status
Research Group Representative ->> Member n: Request Capability Status
Member 1 ->> Research Group Representative: Provide Capability Status
Member n ->> Research Group Representative: Provide Capability Status
Research Group Representative ->> Researcher: Provide Capability Overview
```