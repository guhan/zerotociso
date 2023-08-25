# Code Reviews

## Fagan Review
A Fagan code review, also known simply as Fagan review, is a formal and systematic process for 
reviewing and inspecting source code, with the goal of identifying defects, errors, and quality 
issues. The Fagan review process is named after its creator, Michael Fagan, who introduced it in 
the 1970s as a way to improve software quality and reduce defects in the early stages of development.

Fagan reviews are characterized by their structured and methodical approach, involving a group of 
individuals who thoroughly examine the code to identify issues and suggest improvements. The review 
process is formalized and follows a well-defined set of steps. It is intended to catch defects 
early in the development process, before they can lead to more significant issues later on.

The typical steps in a Fagan code review include:

- **Planning**:
Define the scope of the review, including the code modules or components to be reviewed, the
reviewers, and the review objectives. The planning phase sets the expectations for the review process.
- **Preparation**:
The author of the code prepares a document that provides an overview of the code changes, any
associated requirements, and relevant documentation. This document is distributed to the
reviewers before the review meeting.
- **Inspection Meeting**:
Reviewers come together for a formal inspection meeting. The author presents the code changes,
and reviewers examine the code and related documents. The focus is on identifying defects,
inconsistencies, violations of coding standards, and potential improvements.
- **Individual Review**:
Before the inspection meeting, reviewers individually review the code and documentation to
identify defects and prepare questions or comments. This ensures that reviewers come to
the meeting well-prepared.
- **Review Meeting**:
During the inspection meeting, the author explains the code changes, and reviewers discuss
the findings from their individual reviews. Defects, issues, and suggestions are documented.
The goal is to reach a consensus on the identified issues and agree on corrective actions.
- **Rework and Follow-Up**:
After the review meeting, the author addresses the identified defects and issues. This may
involve making corrections, clarifying code, or addressing concerns raised during the review.
The reviewers may also provide feedback on the rework.
- **Management Reporting**:
The results of the review, including identified defects and actions taken, are documented
and reported to management. This provides transparency into the quality of the code and
the effectiveness of the review process.

Nowadays, the meetings are done asyncronously via the repository host like Github. Comments and changes are 
added to the Pull Request (PR) and the original author can make the necessary changes. 
