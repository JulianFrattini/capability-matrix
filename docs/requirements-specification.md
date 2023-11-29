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

## Usage Model

_This content item details the use case overview of the system vision in its use cases. We distinguish services and use cases (or user stories respectively). Both concepts are means to describe (black box) system behaviour. Use cases describe sequences of interaction between actors (realising user groups) and the system as a whole._

### UC1: Recording Evidence

| UC1 | Recording Evidence |
|---|---|
| Actors | Researcher |
| Pre-conditions | The researcher is authenticated and has a valid, digital evidence |
| End conditions (success) | The evidence is recorded and associated with the researcher |
| End conditions (failure) | The evidence is either not recorded or not associated with the researcher |
| Steps | 1. If a researcher presses "Add evidence", the system opens a dialog window with a dropdown menu for the evidence type. |
| | 2. When the researcher selects the evidence type, the dialog window is populated with input fields of the respective attributes of the evidence type. |
| | 3. When all mandatory input fields contain valid values and the the researcher presses "Confirm", the system records the evidence and associates it with the researcher. |
| Extensions | 2.b. If the researcher presses "Report missing evidence", the system forwards them to an issue reporting interface. |

### UC2: Check capability evidence

| UC2 | Check Capability Evidence 
|---|---|
| Actors | User of the system (Funding Agency or Practitioner) |
| Pre-conditions | The system currently visualizes at least one researcher and their overall ranking in regard to a capability |
| End conditions (success) | The user sees a list of items providing evidence for the capability. |
| Steps | 1. If a user clicks on the capability ranking of a researcher, a window lists the top five most recent items of evidence for that capability. |
| Extensions | 2. If a user clicks "expand", the window shows all items of evidence for that capability. |
| | 1.b. If the administrator configured to show the strongest instead of the most recent items of evidence and a user clicks on the capability ranking of a researcher, a window lists the top five strongest items of evidence for that capability. |

### UC3: Get capability overview

### UC4: Identify capability gap

### UC5: Find expert in a field

### UC6: Organizing capabilities
Only Create (C) use cases are explicitly defined here. Update (U) and Delete (D) need still to be defined and shall not contradict/invalidate Create use cases.

| UC6a | Create capability group |
|---|---|
| Actors | Admin |If the capability group name exists already, the system prevents the Admin from creating the capability group. |
| Pre-conditions | The admin is authenticated and has a valid, digital evidence. |
| End conditions (success) | The capability group is created. |
| End conditions (failure | The capability group is not created. |
| Steps | 1. If an Admin presses "Create capability group", the system opens a dialog window with information fields required for a new capability group. |
| | 2. The Admin enters the information for a new capability group: name, description, and importance (I forgot what we thought about this attribute). |
| | 3. The system checks whether the capability group name is unique and whether similar capability group names or capability names already exist. |
| | 4. The Admin presses "Save" and the new capability group is created. |
| Extensions | 3.a. The system lists similar capability group names and capability names. |
| | 3.b. If the capability group name exists already, the system prevents the Admin from creating the capability group. |
| | 4.a. The Admin presses "Cancel" and the new capability group is not created. |

| UC6b | Create capability |
|---|---|
| Actors | Admin |
| Pre-conditions | The Admin is authenticated and has a valid, digital evidence. |
| End conditions (success) | The capability is created. |
| End conditions (failure | The capability is not created. |
| Steps | 1. If an Admin presses "Create capability", the system opens a dialog window with information fields required for a new capability. |
| | 2. The Admin enters the information for a new capability: name, description, capability group, and allowed evidence types. |
| | 3. The system checks whether the capability name is unique and whether similar capability names already exist. |
| | 4. The Admin presses "Save" and the new capability is created. |
| Extensions | 3.a. The system lists similar capability names. |
| | 3.b. If the capability name exists already, the system prevents the Admin from creating the capability. |
| | 4.a. The Admin presses "Cancel" and the new capability is not created. |

The following UC increases extensibility as evidence types do not have to be defined during system development. Admins can create/update/delete evidence types at run-time.

| UC6c | Create evidence type |
|---|---|
| Actors | Admin |
| Pre-conditions | The Admin is authenticated and has a valid, digital evidence |
| End conditions (success) | The evidence type is created. |
| End conditions (failure | The evidence type is not created. |
| Steps | 1. If an Admin presses "Create evidence type", the system opens a dialog window with information fields required for a new evidence type. |
| | 2. The Admin enters information for a new evidence type: evidence type name, attributes, attribute types. |
| | 3. The system checks whether the evidence type name is unique. |
| | 4. The admin presses "Save" and the new evidence type is created. |
| Extensions | 3.a. The system lists similar evidence type names. |
| | 3.b. If the evidence type name exists already, the system prevents the Admin from creating the evidence type. |
| | 4.a. The Admin presses "Cancel" and the new evidence type is not created. |
