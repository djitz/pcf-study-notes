
### pluralsight recap

- What are some challenges with regards to Monoliths as it applies to developing and managing Monoliths in the cloud?

> Usually monoliths aren't appropriate for cloud due to some anti-patterns

-- Passing around session state among application servers and not persisting that to an external service

-- Writing to disk and counting on that disk to always be there

-- Resources are ephemeral in the cloud

-- Monoliths couple change cycles together

-- Can't be scaled independently -- inefficient scaling

-- Managing team coordination due to the number of developers in the codebase

-- Long term commitment to the technical stack

- How do Microservices differ from a SOLA or ESB approach?

> No central orchestrator between all the different services

> Microservices know how to discover one another and interact with each other without a central coordinator

- What is a bounded context?

> Having a holistic unified enterprise data model is impossible and not cost effective

> Certainly having a unified data model under one specific context is possible

> Each bounded context can have its own view of what a model is and what a model really means

- How can the move to Microservices affect your team structure?

> With the move to Microservices, there's a need to shift to a DevOps type culture, and start to organize around business capability teams

- What are some characteristics of a Microservices architecture?

> There can be polyglot persistence.

> There can be choice in terms of what language to use - runtime layer

> Use of cloud friendly protocols (HTTP, AMQP) - anything that's not technology specific

> Decoupled chain cycles

> Efficient scaling - scale the right thing

> Smaller codebases to learn so developers can get up to speed more quickly


- How does Pivotal Cloud Foundry address some of the challenges with Microservices?

> Dynamic routing when you bring an application up

> Scale out application

> Monitoring the services through logs and cf events

> Service marketplace where you can provision services for polyglot persistence

> The platform is designed to keep your appications up with the four levels of high availability

> Buildpacks offer consistent way to recreate application droplets and know that what you're running is being built out the proper way
