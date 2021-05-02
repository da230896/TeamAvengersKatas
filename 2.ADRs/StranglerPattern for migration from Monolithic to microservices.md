# Record architecture decisions

## Topic

<b>Use StranglerPattern for migration from Monolithic to Microservices</b>

Date: 2021-05-01

## Status

Accepted

## Context and Problem Statement

Monolith is the original application developed to support SysOps squad. It contains all operational info (Customer, Billing info, customer's support plan, Expert and their skillset, KB)

However, there are reliability & elasticity issues due to spike in usgaes and the number of customers using the system. We believe the monolith was built to a specific capability which was exceed during the spike conditions.

We want to rearchitect the Sysops squad to handle the elasticity and reliability. 

## Considered options

1. Rewrite the sysops squad as greenfield applictaion.
2. Migrate the monolithic using strangler pattern (https://martinfowler.com/bliki/StranglerFigApplication.html) towards microservices incrementally. (Recommended)

## Decision

We want to break the Monlithic Sysops squad application to microservices based architecture. This way we can independently scale and deploy the microservices to handle the appropriate load. 
Strangler Pattern will us used to move towards microservices incrementally.

## Consequences

This allow us to replace functionality over time without requiring a big bang rewrite. 
The plan is to get most benefit by identifying the bounded context which is having lot of problem and move it to seperate microservice. In Sysops squad we are planning to move out ticketing service and assignment workflow service outside of the monolithic. We are also planning to split the monolithic database schema out to respective microservice per database.
Extracting Ticketing service from the monolithic can be done in following steps,


- Split the code and convert ticketing service into a separate, loosely coupled module within the monolith
- Split the database and define a separate schema for ticketing service management.
- Define a standalone Ticketing Service
- Use the standalone Ticketing Service
- Remove the old and now unused Ticketing management functionality from the Sysops monolith


**Pros:** 

We plan to decompose our system by finding microservice/seam along which service boundaries can emerge and this has to be an incremental approach. 
By doing this ,
 - We reduced the overall cost of splitting our services 
 - Learn from mistakes quickly 
 - Identify the right bounded context 
 - Test is throughly ,
 - Incrementely deploy new services. 
 - This will also improve the time to market.


**Cons:** 

Maintaining both Monolithic and Microservices at same time could be challenging in terms of deployment , scalability , integration , migration and database sync.

**Risks:** 

Carefully need to manage redundant or overlapping functionality in two different solutions. Migration of existing database schema and data will be challenging if not planned better.


**References:** 

-   https://martinfowler.com/bliki/StranglerFigApplication.html
-   https://docs.microsoft.com/en-us/azure/architecture/patterns/strangler-fig
