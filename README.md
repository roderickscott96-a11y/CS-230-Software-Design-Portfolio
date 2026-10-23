# CS 230 Portfolio — The Gaming Room

This repository contains my completed software design document for **Draw It or Lose It**, created for The Gaming Room in CS 230. The document demonstrates my ability to analyze requirements, apply object-oriented design patterns, compare operating platforms, and recommend an architecture for a distributed web application.

## Portfolio Artifact

- [Completed Software Design Document](Roderick_Scott_CS230_Complete_Software_Design.docx)

## Briefly summarize The Gaming Room client and their software requirements. Who was the client? What type of software did they want you to design?

The Gaming Room was the client, and it wanted to expand its Android game, *Draw It or Lose It*, into a web-based application that could run on multiple platforms. The game needed to support several games at once, multiple teams in each game, and multiple players on each team. Game and team names had to remain unique, and each game, team, and player needed a unique identifier. The design also had to keep game timing and shared state consistent for users connecting from different devices.

## What did you do particularly well in developing this documentation?

I did particularly well at connecting the client's requirements to specific design decisions. Instead of only recommending technologies, I explained why a centralized Java service, a responsive browser interface, PostgreSQL, and Linux would meet the needs of the game. I also clearly described how the Singleton, iterator, and inheritance patterns support controlled service access, unique-name checks, and reusable entity behavior. The document was organized for both the client and the development team, so it explained the business value along with the technical details.

## What about the process of working through a design document did you find helpful when developing the code?

The design document helped me understand the purpose of each class before writing or revising the code. The domain model made it clear that `Entity` should contain the shared ID and name fields, while `Game`, `Team`, and `Player` should inherit that behavior. Writing the requirements and constraints first also showed where validation belonged and why duplicate-name checks were necessary. This reduced guesswork because the code could be compared against an agreed design instead of being developed one class at a time without a larger plan.

## If you could choose one part of your work on these documents to revise, what would you pick? How would you improve it?

I would revise the system architecture section by adding a more detailed deployment diagram. The document explains the browser, Java service, database, object storage, load balancer, and real-time communication components, but a visual diagram would make their connections easier to understand. I would also add a request flow showing how a player's action moves from the browser to the API, through validation and authorization, and into persistent storage. This would make the design more useful during implementation and troubleshooting.

## How did you interpret the user's needs and implement them into your software design? Why is it so important to consider the user's needs when designing?

I translated each user need into a design rule. Cross-platform access led to a responsive browser client. The requirement for unique names led to iterator-based searches in the prototype and database uniqueness constraints in the production recommendation. Timed rounds and multiplayer play led to a server-authoritative design so clients cannot create conflicting clocks, scores, or turns. Considering user needs is important because technically correct software can still fail if it is confusing, unreliable, slow, or unavailable on the user's device. The design must solve the client's actual problem rather than simply use interesting technology.

## How did you approach designing software? What techniques or strategies would you use in the future to analyze and design a similar software application?

I began by separating functional requirements, such as teams, players, timing, and unique names, from quality requirements involving security, scalability, reliability, and platform support. I then used a UML domain model to assign responsibilities to classes and selected design patterns only where they solved a specific problem. After that, I compared deployment platforms and considered storage, memory, networking, security, and cost as parts of one system.

For a similar project, I would continue using requirements traceability, UML diagrams, object-oriented principles, design patterns, and incremental testing. I would also create user stories and acceptance criteria earlier, build a small proof of concept for the highest-risk features, and use automated tests to verify business rules. Finally, I would review the design with both technical and nontechnical stakeholders before implementation so misunderstandings can be corrected while changes are still inexpensive.
