---
layout: post
title:  "Microservices Architecture Pattern"
date:   2022-02-08 22:39:24 -0500
categories: post
---

Overview
* Separatedly deployed units. This allows easier deployment through an effective and streamlined delivery pipeline, increased scalability.
* Concept of service component : contains one or more modules that represents either a single purpose function or an independent portion of a large business application.
* Distributed architecture : Services components are fully decoupled form one another and they are connected through a particular remote access protocol, such as REST, SOAP, JMS, AMQP

Microservices architecutre was emerged to solve challnges from monolith layred architecture pattern and service-oriented architecture pattern.

Monolithic applications typically consists of tightly coupled components in a single large deployable unit. This makes the software difficult to change, test, and deploy, which results to common monthly deployment cycles. Microservices architecture pattern addresses this issue by separating the application into multiple deployable units (service components) that can be individually develeoped, tested and deployed independent of other service components.

While service-oriented architecture (SOA) is powerful and offers unparalled levels of abstraction, heterogenous connectivity, service orchiestration, it is complex, difficult to understand and implement, and usually overkill for most applications. Microservices architecture eliminates orchestration needs, and simplifies connectivity and access to service components.

Pattern Topologies
There are many ways to implement microservies archiecture pattern, but this section introduces the three most popular topologies. Service components tend to be more fine-grained. 

API REST-based Topology
Service components are accessed through a REST-based interface from a separately deployed API layer.

Application REST-based Topology
Clients requests are coming through a web-based or fat-client business application screens. This user interface layer of application is deployed as a separate web application which access service components through REST-based interfaces. Services components tend to be larger than those of API REST-based topology. This topology is common for small to medium-sized business applications with a relatively low degree of complexity.

Cenralized Messaging Topology
This topology is usually found in large business applications required more sophisticated control over transport layer between user interface and service components. Advantage of this topology is advanced queueing mechanisms, asynchronous messeging, monitoring, error handling, better load balancing and scalability.


Avoid Dependencies and Orchestration
One of the main challenges when designing an application with microservices architecture pattern is to decide the granulrity of a service component. If a service component is too coarse-grained, then it is hard to realize the benefits of the microservices architecture pattern, such as deployment, scalability, loose coupling. If a services component is too fine-grained, then you may need orchestration amongst service component, which will become more like a heavy-weighted service-oriented architecture.

Inter-service communication would cause undesired couplings between components. This can be handled through a shared database.

Microservices architecture may violate DRY (Don't Repeat Yourself) principle to handle shared functionality issues, in which a functionality is required on multiple service components. This is fairly common practice in most business applications, trading off redundancy of businss logic for sake of keeping the service components independent of one another.]

If you find yourself not being able to avoid the orchestration regardless of the granularity of service components, it is a sign that microservices architecture might not be a right architecture for the application. Because of the distributed nature of this pattern, it is difficult to maintain a single transactional unit of work across service components. such a practice would require some sort of transaction compensation framework for rolling back transactions, which adds significant complexity to the architecture pattern.