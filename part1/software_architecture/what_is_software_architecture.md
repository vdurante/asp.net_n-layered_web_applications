# What Is Software Architecture
> Software application architecture is the process of defining a structured solution that meets all of the technical and operational requirements, while optimizing common quality attributes such as performance, security, and manageability. It involves a series of decisions based on a wide range of factors, and each of these decisions can have considerable impact on the quality, performance, maintainability, and overall success of the application.
> -- <cite>Microsoft Application Architecture Guide, 2nd Edition</cite>

Whenever building a software, important decisions must be taken in order to achieve the great goal: success. Between these decisions, the important ones are:

* **Quality attributes.** Selecting non-functional requirements to evaluate the performance of the system .
* **Environment.** Choosing the right infrastructure, regarding software, hardware, network and services. The environment must satisfy the requirements of the desired system.
* **Design.** Description of the elements of a system. Defining how these elements fit together and  interact with each other.
*  **Human interaction.** How humans fit inside the system, whether they are stakeholders, developers or users.
*  **Business strategy.** Defining strategies that allow the organization to achieve its long-term objectives.

 ![teste](./resources/img/figure1.png) 
 
It is part of software architecture defining a architecture that will satisfy user, business and system goals. It is a hard balance to achieve.

## Goals of Software Architecture

It is important to address the main goals of software architecture:

* **Expose the structure of the system.** Avoid implementation details.
* **Address requirements of stakeholders.**
* **Address all use-case scenarios.**
* **Handle functional and quality requirements.**
* **Be flexible.** Being able to easily handle the recurring mutability of the software.

## Key Architecture Principles

Some key principles must be kept in mind when designing an architecture:

* **Focus on change instead of durability.** Applications constantly change with time. Building a flexible application is crucial.
* **Model to analyze and reduce risks.** Modeling the architecture using tools like the Unified Modeling Language (UML) helps the visualization of the system, facilitating the understanding of the system as a whole. Being prepared for the risks that may arise is also important to avoid problems.
* **Communication.** Stakeholders must be easily aware of the architecture.
* **Identify great engineering decisions.** Knowing to identify and avoid the most common mistakes.
* **Recursive and incremental strategy.** Building cycles of development focused on creating, modifying and refactoring features or components.

In short, it falls back to software engineering: plan and document everything prematurely, otherwise a drastic change may result in high expenses of time and money for the team.