# Software Design Lifecycle 

- **Phase 1**: Gathering information and determining the scope of the project

- **Phase 2**: Taking in requirements and determining if resources (time, money) are sufficient

- **Phase 3**: The System design phase

- **Phase 4**: Building the Software

# Top-Down vs Bottom-Up

- Top-Down design consists of creating a data model based on requirements

- Top-Down design is for brand-new projects; Bottom-Up is for when there's an existing system or specific data already in place.

# Entities

An entity is:

- A person, place, or thing
- has a singular name
- has an identifier
- should contain more than one instance of data

# Scalability

-Vertical scaling is when you rely on getting more powerful computers to get the job done
    -Is generally quicker than horizontal scaling
    -Disadvantages to this approach include a single point of failure

-Horizontal scaling is when you rely on a greater quantity of computers to get the job done
    -Is generally slower than vertical scaling
    -Scales well as users increase
    -Disadvantages to this approach include the need for load balancing, and data inconsistency

# Load Balancing

-Load balancing is the practice of trying to even out, or "balance the load" of requests between machines/servers responding to that request.

# Consistent Hashing

-Consistent hashing is what we call the practice of hashing distributed servers in a manner that allows the system to reconfigure requests in an even manner when new servers are added to the system.

# Message/Task Queue

-These handle the order and priority of incoming/outgoing tasks

# Monoliths vs Microservices

## Monoliths

-The advantages of a monolith architecture are:

- Better for smaller teams
- It has fewer moving parts

-The disadvantages of a monolith architecture are:

- More difficult to onboard new team members
- Requires more frequent and fragile deploys
- It has a single point of failure that will bring everything crashing down if one thing is broken.

## Microservices

-The advantages of a microservice architecture are:

- Easier to scale
- Easier to onboard new team members
- Fewer dependencies/tight code coupling
- Easier to reason about

-The disadvantages of a microservice architecture are:

- More difficult to initially design
- Harder to justify the fewer individual services interact within the architecture

# Sharding

- Horizontal Partitioning aka Sharding is distributing parts of the data among different machines
- Consistency trumps Availability of data in most cases
- 



