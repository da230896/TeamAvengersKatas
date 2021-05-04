# Record architecture decisions

## Topic

<b>Load Balancer in front of Ticket Service to scale</b>

Date: 2021-05-01


## Status

Accepted

## Context and Problem Statement

Existing Sysops mainly has problem of availability during skipe in load.

## Considered options

- Able to scale capacity of ticket services horizontally.

## Decision

We plan to address the problem by providing mulitple instances of the ticket services and distribute load across different machines. We can add more servers to handle the capacity skipe. We will calculate the capacity and add servers as needed. It will be completely manual in the beginning. We can later maintain kubernetes to spawn servers when in demand.

## Consequences

Having loadbalancer infront of ticket creation service will able to auto-scale when the burst of ticket request happens. The ticket creation service elasticity problem is solved. 


**Positive:** 

 - Will be able to handle the load during the spike with multiple servers with proper distribution of load 

**Risks:** 

 - Servers maintained for high peak time, might be idle other time.

