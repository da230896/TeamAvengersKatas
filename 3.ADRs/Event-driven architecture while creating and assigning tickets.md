# Record architecture decisions

## Topic

<b>Event-driven architeture while creating and assigning tickets</b>

Date: 2021-05-01


## Status

Accepted

## Context and Problem Statement

Existing Sysops squad monolithic applictaion is having problems related to ,

- Elasticity : due to burst of  ticket requests from multiple customer
- Reliability :  wrong ticket consultant assignment issue
- Availability : system is not available for web-based / call center ticket entry 

We plan to address the above problems by leveraging event driven architecture while creating tickets.

## Considered options

- Leverage message bus such as Apache Kafka to decouple ticket creation service and ticket workflow (assignment) service. Also handle the burst ticket creation scenario.

## Decision

We seperated two main components ticket creation service and ticket workflow (assignment) service. We introduced the message bus (Apache kafka) to handle the elasticity (burst of tickets create request). We can scale  ticket creation service independently of ticket assignment service to handle the load of customer ticket request . We can aknowledge the reciept of ticket creating request immediately to customer by storing that in database and publishing the message to the queue. The ticket assignment service will consume the message and hold on the distributed lock on the expert until the ticket assignment , persistance and ticket notification complete.

## Consequences

Having loadbalancer infront of ticket creation service will able to auto-scale when the burst of ticket request happens. The ticket creation service elasticity problem is solved. By publishing the 'ticket_creation' event over message bus it decouples both creation and assignment service and can independently worked.


Ticket assignment reliability is more critical and it is solved be using distributed lock on expert. When two or more instances of ticket workflow service are running and planning to execute assignment algorithm , only one instance will hold distributed lock on the matched expert and release when the assignment , notification is complete. This will definately solve wrong expert assignment sysops squad issue.  


**Positive:** 

 - Ticket creation service can be independently scale and handle the elasticity and scalability issue.
 - By leveraging distributed lock , we ensure only one expert is in action during ticket assignment. Data reliability of ticket assignment shall be solved.
 

**Risks:** 

 - Adding one more component (message bus) will introduce failure point and needs to ensure availabiilty of the same.
 - Message duplication , message lost scenarios needs to be handled and implemented.


