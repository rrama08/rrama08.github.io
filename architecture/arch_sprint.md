---
layout: default
title: LAMA
permalink: /lama/
published: true
---

# Lean Architecture Method for Agile
I have been lately doing some thinking on a better approach for integration of holistic systems thinking and architecture into agile execution with out impacting speed and agility. I have built a rough outline of a process that can be used with low friction and considerable value to the overall system. I call this the Lean Architecture Method for Agile (LAMA)

7 Key principles of LAMA are:
1. **Collaborate on Architecture:** Architecture is a collaborative process. There is no room place for Ivory tower architectures in modern software development.
1. **Think Systemically:** Think and establish clear principles at a system level, act locally at the Sprint team level.
1. **Preserve Optionality:** Preserve optionality on some design decisions till they start impacting deliverables, but make obvious design decisions early to reduce ambiguity and keep the decision space lean and focused.
1. **Keep Architecture Flexible:** Architecture should be done iteratively (No big Upfront Design) and should be weaved into the execution. Architecture must be flexible to be updated as the team learns through the project.
1. **Log Architecture Decisions:** Keep a catalog of architecture decisions as a fluid list. They will act as a guideline with the Agile teams. The best log is version controlled similar to code.
1. **Create an Architecture Story:** Have an approach to effectively communicate the architecture to wider audience. An architecture not communicated is an architecture that is not implemented as intended.
1. **Encourage Architecture Huddles:** Establish a practice of periodic architecture huddles, to update assumptions, confirm/re-confirm decisions, and ensure alignment between all parties.

## How is the LAMA initiated?
LAMA is initiated with a 5 day Architecture Immersion Sprint (AIS) with clear objectives and deliverables for each day and a deliverable at the end of the 5 day effort. The AIS is intentionally set across multiple days to give participants plenty to time to reflect and think independently and with in teams. For smaller projects, part of the day can be used, but I would recommend to keep the process to 5 days.  

![Immersion Process](/assets/images/Lamaimmersion.png)

As the output of the AIS, the team should have a comprehensive view of the architecture represented by multiple view points.

![Architecture States](/assets/images/ArchitectureViews.png)
## LAMA  team
The architecture immersion sprint team consists if the following team members for a development org with multiple sprint teams and a product architect or senior developer who acts as a lead across teams. Depending upon the structure of the organization this can be adjusted for a single sprint team to include all members of the team.

1. SCRUM Master/s
1. Product Owner/s
1. Product Architect
1. Technical representative from each development sprint team. For small teams, all team members may be invited.

## LAMA Architecture Immersion Sprint
The process is done across 5 days. In preparation for this you need the following:

1. A Conference room with plenty of whiteboard space and space for Sticky notes.
1. A good widescreen TV for projecting screens
1. A good collaborative document editing software such as Google Doc/Atlassian Confluence/Wiki etc
1. A Shared directory such as Google drive, Box, Drop Box etc where a LAMA directory has been setup to store all artifacts
1. An Architecture Story document created to capture the discussion outputs

### Monday - Functional Immersion
Establish the baseline understanding of the product across all members of the audience, to ensure that everyone has the same basic understanding of the system. The activities of this day include

**Objective:** Achieve functional clarity of the system across all team members

* Creating or Articulating (if it has already been created) the product vision statement
* Define all the user personas of the system
* Create a functional decomposition of the system into groups of functions which act as a pre-cursor to the user stories. The functions are broken down to the epic level
* Understand and group and re-group functions till a sufficiently optimal grouping of functions is achieved
* Debate initial priority of the functions of the system
* Debate relevance of functions
* Discuss the timeline imperatives of when the MVP should be launched. This will help in prioritization as well as some architecture discussions on what architecture will be used.

At the end of day 1 the team should have a complete understanding of the functionality of the system at a feature/epic level and should have a great start in the process of defining user stories for the system.

**Output:** A functionally hierarchical view of the system, and an initial skeleton of a product story that describes the purpose and vision of the system.

### Tuesday - Conceptual Immersion
The second day is all about debating, drawing and re-drawing the conceptual view of the architecture. Every participant including the product manager can and should participate in this exercise.

**Objective:** Achieve conceptual clarity of the system across all team members

* Kick off Discussion (captured in sticky notes and grouped into one section of the room. Alternatively, a google doc or a collaborative editing software may also be used)
  * Baseline principles of the architecture (Add this to the Architecture Story).
  * The known Non functional requirements and constraints known at the second day (Add this to the Architecture Story).
  * Major patterns & blue print of the architecture (Micro-Services, Fast Data, Reactive etc)
  * Build the conceptual architecture
  * All team members independently draw they perspective of the architecture based on the kick off discussion. Based on what each team member is comfortable with they can use pen & paper, ppt, ipad drawing apps etc
  * The Conceptual view must stay away from representing aspects of technical architecture, unless there is a pervasive understanding of the stack in the org.
* Conceptual Architecture Presentation
  * Each team member will present their view of the conceptual architecture and others ask questions and clarifications till sufficient detail is drawn out
* Collaborative creation
  * At the end of the day the team collaboratively creates the architecture. The drawing may be done by some one with good Powerpoint/Keynote skills, but the process is collaborative. The person who builds the drawing is also responsible for taking the drawing away at the end of the day and polishing it to make it a polished looking view of the architecture

**Output:** Conceptual architecture view of the system in the form of a widely shareable format (PPT, Keynote) that can be used in presentations and communications. This document is added to the shared drive.

### Wednesday - Technical Immersion
The 3rd day is all about defining the technical Architecture of the system. This is where the technical members of the team should take the lead and start making basic decisions about the technical stack that can meet the functional and non-functional requirements and meet the needs of the project.

**Objective:** Achieve technical clarity of the system across all team members

* Kick off discussion
  * 15 Min review of the conceptual architecture diagram created the previous day and reaffirmation of all the decisions from prior day.
  * Discussion of the non-functional requirements of the system. System Availability, performance and other 'ilities may be discussed here (Add this to the Architecture Story).
* Debate the technical Architecture
  * The team members should start discussion of potential frameworks, architectures, tech stack (Java/Node/Rails/LAMP etc), Data bases, Storage, Caching systems etc.
  * Proponents of each stack should give their reasoning and the team should have opportunity to ask questions and weigh the pros and cons of the stack. Considerations should include
    * Existing knowledge in the organization
    * Prior experience with the stack
    * Industry comps for similar products
    * Potential disruption opportunity. for e.g. Using Spark Data streaming and processing to create a billing system that can disrupt traditional approaches.
* Outline the technical Architecture
  * The team outlines the technical architecture as bullet points captured in the Architecture Story document. In some areas they may be ready to make decisions on the technical architecture, where as in other areas they may choose to preserve optionality that can be resolved through technical spikes executed during Sprints.
  * It is not necessary to create a diagram to represent the technical architecture. The technical architecture can simply be captured as a series of bullet points.

**Output:**
* A brief bullet point format list of technical architecture along with any optionalities that will be decided later described in text in the Architecture Story document.
* Any decisions captured as a part of the decision log

### Thursday - Runtime Immersion
Day 4 is all about running and the run time architecture

**Objective:** Achieve operational clarity of the system across all team members

* Kick off discussion
  * Review non functional requirements related to run time and operational aspects including availability, scalability, manageability and maintainability.
  * Discuss non functional constraints (for e.g. Data storage in cloud/ Any constraints caused by the Clients including regulatory/HIPPA/PCI compliance etc)
  * Discuss anticipated computing and storage growth needs and volumetrics of the system
  * Discuss Run time architecture principles including containerization
  * Discuss automation needs and principles (Build, test, performance, deployment automation)
  * Discuss environment types needed
  * Discuss the Deployment cadence requirements (Continuous Delivery vs Deployment)

All relevant portions of the above topics should be added to the Architecture Story document.

* Outline the Run time architecture
  * The team should debate the pros and cons of the possible run time architecture options. At this stage, it may be beneficial to draw a decision tree on the board that may help through the discussion.
  * The team should select a good enough approach for the run time architecture with the understanding that this decision may be reviewed and modified at a later time. At this stage, the decision could almost be a gun point decision of the run time architecture
  * Document the decision as simple bullet points in the Architecture Story


**Output:**
* A brief bullet point format description of the run time architecture
* Any decisions captured as a part of the decision log

### Friday - Presentation
This day should be focused on presenting the architecture to a wider audience not in the room. This includes
* Architecture and technical experts from other parts of the company who may be able to contribute
* All the team members
* Executives and leaders from the organization who are involved or are stake holders of the project.

*Objective:* Achieve architecture clarity of the system across a wide audience of stakeholders, team members and contributors.

This day should be set into 2 Parts

First half of the day should be focused on creating a presentation of the architecture using all the material created from 4 days of discussion. One of the team members who have good presentation building skills should drive the creation of the presentation and the team should designate some one who will lead the presentation. Everyone contributes to the presentation. Some guidelines:
* Keep the slides to a maximum of 10 slides
* Use big fonts and plenty of pictures
* Favor simplicity instead of exhaustiveness. Address details in questions and answers and use the Architecture story to answer questions.

The Second half of the day should be reserved for the pre-scheduled presentation. All questions and answers should be scribed into a Q&A Section of the Product Story for later use and clarity. The team should feel accomplished after an exhaustive 5 day process and should feel a sense of complete expertise of the system and the approach used to build the system.

## After the Architecture Immersion Sprint

![Image Placeholder](/assets/images/lamaprocess.png)

The Architecture must continue to be developed and refined through the execution process through a series of one day LAMA Huddles. These are one day events where a specific area of architecture is explored and disambiguated further. the LAMA Huddles must be spread across the execution of the Sprint. A good example for such a huddle is for the Data or Domain model review once the teams have put together their domain models. I recommend a huddle initially once in 2 Sprints and subsequently once every 3 or 4 sprints.

The team will typically navigate between LAMA huddles and development sprints as shown below

![LAMA States](/assets/images/lamastates.png)

## Benefits of LAMA
I will conclude with the benefits of the LAMA Process for the organization

1. Diffusion of Knowledge through upfront collaborative thinking. This leads to better decisions, less waste and faster delivery of value.
2. Zero disruption to agile. This process works seamlessly with agile and weaves to existing agile practices.
3. The process de-risks the agile project further with a small amount of upfront strategy and systems thinking and reduces future technical debt

## Acknowledgements
* This concept has been inspired by the Design Sprint approach by Google Ventures [Link](http://www.gv.com/sprint/)
* Integrating architecture into Agile has been well documented in couple of practices - SAFE and DAD. What I am proposing a lighter weight approach that may be suitable/sufficient in many cases
  * [SAFE](http://www.scaledagileframework.com)
  * [DAD](http://www.disciplinedagiledelivery.com)
