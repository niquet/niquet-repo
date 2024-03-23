# Design Doc
This is a template for design docs (also known as RFCs). It is not meant to be exhaustive, but to help you think better about the problem and design. Adopt whichever sections – and add new sections – to meet this goal.

**Tips**
- Design docs are informal documents, write them in whatever form makes the most sense for the particular project
- If the design problem is not ambiguous, then there is little value in going through the process of writing a doc.
- If a doc basically says “This is how we are going to implement it” without going into trade-offs, alternatives, and explaining decision making (or if the solution is so obvious as to mean there were no trade-offs), then it would probably have been a better idea to write the actual program right away.
- Additionally, the overhead of creating and reviewing a design doc may not be compatible with prototyping and rapid iteration. However, most software projects do have a set of actually known problems.
- Additionally, prototyping itself may be part of the design doc creation. “I tried it out and it works” is one of the best arguments for choosing a design.
- Describe the high-level implementation strategy and key design decisions & trade-offs that you considered.
- Focus on solving a specific problem and investigate possible solutions, and explain the details of the chosen approach.
- Keep the template simple and prefer good over perfect.
- Design docs should be short enough to actually be read by busy people.
- As plans collide with reality, it is inevitable that shortcomings, unaddressed requirements, or educated guesses that turned out to be wrong surface, and require changing the design.
- It is strongly recommended to update the design doc in this case.
- As a rule of thumb: If the designed system hasn’t shipped yet, then definitely update the doc.

**Table of Contents**
- [Motivation](#motivation)
- [Context and Scope](#context-and-scope)
- [Goals and Non-goals](#goals-and-non-goals)
  - [Functional goals](#functional-goals)
  - [Non-functional/technical goals](#non-functionaltechnical-goals)
  - [Non-goals](#non-goals)
  - [Constraints](#constraints)
- [Design](#design)
  - [System-context-diagram](#system-context-diagram)
  - [APIs](#apis)
  - [Data storage](#data-storage)
  - [Code and pseudo-code](#code-and-pseudo-code)
  - [Degree of constraint](#degree-of-constraint)
- [Alternatives Considered](#alternatives-considered)
- [Cross-cutting Concerns](#cross-cutting-concerns)

_**Note:** Remove the above section and replace it with a summary of the doc's purpose, problem, solution, and desired outcome, in 3-5 sentences._

---
## Motivation
Why the problem is important to solve, and why now.

## Context and Scope
Rough overview of the landscape in which the new system is being built and what is actually being built (objective background facts). Some previous knowledge can be assumed and detailed info can be linked to.

Some problems are too big to solve all at once. Be clear about what's out of scope.

## Goals and Non-goals
Bullet points of what the goals and non-goals (things that could reasonably be goals, but are explicitly chosen not to be goals) of the system are.

### Functional goals
- Functional goals are those that should be met to ship the project.
- Describe them in terms of the customer perspective and benefit.
  
### Non-functional/technical goals
- Non-functional/technical goals are those that define system quality and how the system should be implemented.
- These include performance (throughput, latency, error rates), cost (infra cost, ops effort), security, data privacy, etc.

### Non-goals
- Things that could reasonably be goals, but are explicitly chosen not to be goals.
- You might still select a solution that provides it, if it doesn’t introduce trade-offs that prevent achieving the goals.

### Constraints
- Constraints can come in the form of non-functional goals (e.g., cost below $`x` a month, p99 latency < `y` ms).

## Design
Start with an overview and then go into details. Focus on the trade-offs, suggest solutions and show why a particular solution best satisfies the goals.

**This section should answer the majority of the following questions:**
- How will you host your system? On-premise, cloud, or hybrid?
- How will your system meet the throughput and latency requirements? Will it scale vertically or horizontally?
- How will your system/application authenticate users and incoming requests? If it's publicly accessible, will it be behind a firewall?
- How will you ensure the privacy of customer data? Will your system be compliant with data retention and deletion policies
- How will you log events in your system? What metrics will you monitor and how? Will you have alarms if a metric breaches a threshold or something else goes wrong?
- How much will it cost to build and operate your system? Share estimated monthly costs (e.g., EC2 instances, Lambda, etc.)
- How will your system integrate with upstream data and downstream users?
- Risks are the known unknowns; uncertainties are the unknown unknows. What worries you and you would like others to review?

_**Note:** Include the following topics only when they help make sense for expressing the problem set at hand in an appropriate manner._

### System-context-diagram
- Shows the system as part of the larger technical landscape.
- Allows readers to contextualize the new design given its environment that they are already familiar with.

### APIs
- Useful when the system under design exposes an API.
- Do not copy-paste formal interface or data definitions as they often contain unnecessary detail and quickly get out of date.
- Focus on the parts that are relevant to the design and its trade-offs.

### Data storage
- Useful when the system stores data.
- Discuss how and in what rough form this happens.
- Focus on the parts that are relevant to the design and its trade-offs.

### Code and pseudo-code
- Design docs should rarely contain code, or pseudo-code except in situations where novel algorithms are described.
- As appropriate, link to prototypes that show the implementability of the design.

### Degree of constraint
- Degree of constraint of the solution space.
- For a "greenfield software project" – all goals are known, but the solution can be whatever makes most sense – such a document may be wide-ranging, but it also needs to quickly define a set of rules that allow zooming in on a manageable set of solutions.
- For "legacy systems" – the possible solutions are very well defined, but it isn’t at all obvious how they could even be combined to achieve the goals - such a document may be able to enumerate all the things you can do relatively easily, but you need to creatively put those things together to achieve the goals. There may be multiple solutions, and none of them are really great, and hence such a document should focus on selecting the best way given all identified trade-offs.

## Alternatives Considered
Alternative designs that would have reasonably achieved similar outcomes. Focus on the trade-offs that each respective design makes and how those trade-offs led to the decision to select the design that is the primary topic of the document.

## Cross-cutting Concerns
Concerns such as security, privacy, and observability. Relatively short explanation on how the design impacts the concern and how the concern is addressed.

---

## Acknowledgements
- M. Ubl. "Design Docs at Google," Industrial Empathy, Jul. 6, 2020. [Online]. Available: [https://www.industrialempathy.com/posts/design-docs-at-google/](https://www.industrialempathy.com/posts/design-docs-at-google/). [Accessed: Mar. 21, 2024].
- Liam. "StaffEng - How to write a design doc (And How Google does it)," Medium, Aug. 23, 2022. [Online]. Available: [https://medium.com/@liamchzh/staffeng-how-to-write-a-design-doc-and-how-google-does-it-19c495c53fcf](https://medium.com/@liamchzh/staffeng-how-to-write-a-design-doc-and-how-google-does-it-19c495c53fcf). [Accessed: Mar. 21, 2024].
- Eugene Y. "ml-design-doc," Mar. 16, 2023. Available: [https://github.com/eugeneyan/ml-design-docs](https://github.com/eugeneyan/ml-design-docs). [Accessed: Mar. 22, 2024].
- 
- M. Ubl. "Design Docs at Google," Industrial Empathy, May 20, 2015. [Online]. Available: [https://www.industrialempathy.com/posts/design-doc-a-design-doc/](https://www.industrialempathy.com/posts/design-doc-a-design-doc/). [Accessed: Mar. 22, 2024].
