# Tiers

- **Tiers** are components in an application or service that are separated by role, such as database, backend application server, user interface, messaging, caching

- Single-Tier applications are when all components reside in the same device, like most desktop applications.

- These are good for performance and availability of data. These are less good for maintenance, since there's 
nothing to be done after the user buys the software. Think in terms of PS1 games, versus current-gen games which can be patched remotely.

- A two-tier application has a client and a server.

- A three-tier application (think MVC) has the UI, application logic, and database in different machines. 

- An N-tier application (aka distributed application) has more than three components involved.

# Web Architecture

## Client-Server Paradigm

- A Client is what we think of as user-facing: a website, mobile application, etc.

- A Thin Client holds only the UI of the application, no business logic of any kind.

- A Thick Client holds some or all of the business logic.

# High Availability

- "High availability also known as HA is the ability of the system to stay online despite having failures at the infrastructural level in real-time"

- "Fault tolerance is the ability of the system to stay up despite taking hits."

- "Redundancy is duplicating the components or instances & keeping them on standby to take over in case the active instances go down. It’s the fail-safe, backup mechanism."

- 