# Microservices Architecture Course Notes

My notes from the Microservices Architecture course on Pluralsight by Rag Dhiman.

## Introduction

**What Is A Service?**

A software component that provides functionality (provides a 'service') to other software components/applications/systems.

### Service-Oriented Architecture (SOA)

**Key Features:**

* **Scalability** -- a service can be horizontally and vertically scaled
* **Reusability** -- lots of different clients can make use of the same functionality
* **Standardized Contracts (Interfaces)** -- the signature of the public methods don't (normally) change and therefore can be relied upon even if the underlying service implementation changes.
* **Stateless** -- the service doesn't have to remember previous state (from the caller, etc.) -- provided all the necessary data by the client

**Key Disadvantages:**

* Without guidance on how to size a service, traditional services were monolithic

### Microservices Architecture

A modern take on SOA; SOA "done well".

* Knowing how to size a service -- principles for sizing
* Knowing what to include (or not) in a service

**Key Features:**

* **Independently Changeable** -- can be upgraded, fixed, etc. without impact to its clients nor other (micro)services
* **Independently Deployable** -- can be deployed without impact to its clients nor other (micro)services
* **Handle Transactions in a Distributed Fashion** -- one to many microservices will be involved in completing a given transaction (for a given client)
* **Efficiently scalable (horizontally)**
* **Flexible**
* **Highly Performant**
* **Small & Focused** -- does one thing and does it well
* **Lightweight Communication Mechanism** -- communication needs to be fast for both clients and other services
* **Technology Agnostic (API)** -- open communication protocol, etc.

**Key Requirements:**

* **Centralized tooling for management** -- manage, monitor (health), etc.
* **Independent Data Storage** -- don't use a centralized data store

Applications that make use of microservice architecture typically are "powered" by multiple microservices.

### Monolithic System

A typical, enterprise application -- like a large scale web site application (e.g. as.com).

All of the "modules" are all packaged together into one "executable" (unit).

**Key Pros:**

* Easy to replicate the environment

**Key Cons:**

* No restriction on size
* No division or separation between modules; large codebase
* **Chanllenging Development** -- takes longer to develop resulting in longer development times
* **Challenging Testing** -- takes longer to test because there isn't any separation between modules, modules can affect each other (tightly coupled)
* **Challenging Deployments** -- takes longer to deploy since the entire system needs to be deployed everytime
* **Inaccessible Features** -- features that could/would be useful to other clients and services are "trapped" inside the monolith
* **Fixed Technology Stack** -- since the monolith is a set of tightly coupled modules, it is difficult to leverage other technologies; interoperability
* **Tight Coupling** -- modules are intertwined in a way that makes it difficult to make changes to one without affecting others
* **System Wide Failures** -- since the monolith is deployed all together, typically has tight coupling, etc. a failure in one module could and will often affect the entire system (instead of a single module/unit/service)
* **Limited Scalability** -- scaling means duplicating the whole monolith
* **Long Compilation Times** -- even a minor change requires a complete rebuild (in many cases)

### Emergence of Microservices

**Why Now?**

* **Need to respond to change quickly**; more quickly now than ever before
* **Need for reliability** -- by breaking functionality down into small services, failure can be limited or contained to a single area instead of the entire system.
* **Business domain-driven design (DDD)** -- needs to match the organization structure
* **Automated Test Tools**
* **Automated Release and Deployment Tools (CI/CD)** -- build and deploy tools
* **On-demand and Cloud Hosting**
* **Need to adopt new technology**
* **Asynchronous communication technology** -- distributed transactions don't have to wait for each call to communicate
* **Simpler Technology** -- both server side and client side

**Key Benefits:**

* **Shorter development times**
* **Reliable and faster deployment**
* **Enables frequent updates**
* **Decouple the changeable parts** -- think UI
* **Security** -- distributed modules means different modules can handle security differently -- a single security flaw in a monolith would provide access to more "stuff" vs. a flaw in a single module/service
* **Increased Reliability / Uptime**
* **Fast(er) Issue Resolution** -- in theory it should be easier to locate and fix an issue in a single module / service instead of trying to locate it within a monolith
* **Highly Scalable and Performant** -- allows us to scale a service up or out without changing anything else in the system.
* **Better Ownership and Knowledge** -- a single team can own a module or service instead of the entire monolith
* **Technology Options** -- the ability to choose the right technology for the given problem domain instead of needing the stay within the same technology stack.
* **Enables Distributed Teams**

### Microservice Design Principles Introdution

1.  **High Cohesion**
1.  **Autonomous**
1.  **Business Domain Centric**
1.  **Resilience**
1.  **Observable**
1.  **Automation**

#### High Cohesion

* Content and functionality is coherent.
* **Single Focus**
* **Single Responsibility** (SRP -- S in SOLID) -- single reason to change
* **Reason for Change** -- business function, business domain
* **Encapsulation** -- related funtionality in a single module
* **Easily Rewriteable** -- so small it's easy to rewrite
* -ables: Scalable, Flexible, Reliable

#### Autonomous

* **Loose Coupling** -- between clients and services and between services
* **Honor Contracts** (Interfaces) -- even between versions?
* **Stateless**
* **Independently Changeable**
* **Independently Deployable**
* **Backwards Compatible**
* **Concurrent Development**

#### Business Domain Centric

* Service Represents Business Function
* Scope of Service
* [**Bounded Context**](https://martinfowler.com/bliki/BoundedContext.html) (from Domain-Driven Design)
* Identify Boundaries / Seams
* Move Code Around If Required -- group related code into a service

#### Resilience

* **Embrace Failure** -- clients to services, services to one another
* **Degrade Functionality** (Gracefully) -- default functionality
* **Multiple Instances** -- service discovery, load balancing
* **Types of Failure** -- exceptions, errors, delays, unavailability
* **Network Issues** -- delay or unavailability
* **Input Validity** -- client to service, services to one another

#### Observable

* **System Health** -- status, logs, activity, errors, etc.
* **Centralized Monitoring**
* **Centralized Logging**
* **Quick Issue Identification and Resolution**
* **Fast Feedback**
* **Data Captured** -- used for capacity planning, scaling, etc.
* **Monitor, Measure Business Data** -- capture data that is important and valuable to the business

#### Automation

* **Tools to Reduce Testing** -- reduce or eliminate manual regression testing, the time it takes to regress
* **Tools to Provide Quick Feedback** -- automated end to end tests via continuous integration (CI)
* **Tools to Provide Quick Deployment** -- automated deployment via continuous deployment (CD)

## Microservices Design

## Microservices Technology

## Moving Forward

### Brownfield

### Greenfield

## References

### Domain-Driven Design??

#### Bounded Context
