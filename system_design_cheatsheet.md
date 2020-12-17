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
