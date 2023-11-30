# Requirements Specification

_The requirements specification comprehends the requirements on the system under consideration by taking a black-box view on the system. This means, we specify requirements from a user's perspective without constraining (or even without having to understand) the internal realisation of the system. This comprehends, for example, use cases (or user stories, depending on preferences and choices), and non-functional requirements._

## System Vision

_The system vision comprehends the system context of the system under consideration, which is intended to realise a number of features. A feature is a prominent or distinctive user-recognisable aspect, quality, or characteristic of a system. In addition, we specify an use case overview, i.e. a (potentially) graphical overview of the use cases._

![System vision of the Capability Matrix](./../figures/system-vision.png)

### Mapping

The use cases fulfill the goals in the following way:

| UC | Fulfilled Goals |
|---|---|
| UC1 | G3 |
| UC2 | G7 |
| UC3 | G1, G5, G6, G9 |
| UC4 | G2 |
| UC5 | G4, G8 |
| UC6 | |

The goals G10-G12 are currently not addressed by any use case.

### UC3: Get capability overview
| UC3 | Get capability overview
|---|---|
| Actors | (Senior) Researcher |
| Pre-conditions | The researcher is authenticated |
| End conditions (success) | An overview of the capabilities of a research group is generated. |
| End conditions (success) | An overview of the capabilities of a research group is generated. |
| Steps | 1. If (Senior) Researcher presses "Research group overview" the system opens a new window with a table containing the following information about all the researchers belonging to the research group: researcher name, capability groups in which this researcher has capabilities, capabilities this researcher has, link to profile page. |
| | 2. If (Senior) Researcher clicks on the page "Generate visualization" a simple visualization (piechart) of a proportion of table entries in columns capability groups, capabilities is shown. |
| Extensions | 1.a. The (Senior) Researcher can filter table entries in each column. |
| | 1.b. The (Senior) Researcher can sort table entries in each column. |



| UC3 | Get capability overview
|---|---|
| Actors | Researcher |
| Pre-conditions | The researcher is authenticated |
| End conditions (success) | A link to a page with customized portfolio visualization is generated. |
| End conditions (success) | A link to a page with customized portfolio visualization is not generated. |
| Steps | 1. If the researcher clicks on "Visualize portfolio", a new page opens that contains profile information. |
| | 2. The Researcher selects information that he would like to visualize (capability group, capability, evidence). |
| | 3. The system generates a preview of customized portfolio visualization.
| | 4. If the researcher clicks on "Save profile", a dialog window appears containing the URL of the page with personal capability portfolio visualization. |


| UC3 | Get capability overview
|---|---|
| Actors | Practitioner |
| Pre-conditions | - |
| End conditions (success) | The Practitioner finds the profile and contact details of the Researcher for a collaboration. |
| End conditions (success) | The Practitioner does not find the profile and contact details of the researcher for a collaboration. |
| Steps | 1. If the Practitioner clicks on the button "Find a collaborator" a dialog window with a search form opens. |
| | 2. The form allows to execution of a free text search across all the data on capabilities and researchers. In the Practitioner executes the search Practitioner can see results in the form of a table. The table contains the following information: Researcher name, capability groups in which this Researcher has capabilities, capabilities this Researcher has, and link to the profile page. |
| | 3. If the Practitioner clicks on the link to the profile page, the profile page opens where the contact details of the Researcher are available. |
| Extensions | 2.a. The (Senior) Researcher can filter table entries in each column. |
| | 2.b. The (Senior) Researcher can sort table entries in each column. |
