# Record architecture decisions

## Topic

<b>Leverage Orchestration in API Gateway for security requirement</b>

Date: 2021-05-01

## Status

Accepted

## Context and Problem Statement

A microservice-based architecture may have from 10 to 100 or more services. An API gateway can help provide a unified entry point for external consumers, independent of the number and composition of internal microservices.


## Considered options

- Use API Gateway

## Decision


 - API gateways help to prevent malicious attacks by providing an additional layer of protection from attack vectors such as SQL Injection, XML Parser exploits, and denial-of-service (DoS) attacks.
 - We prevents exposing internal concerns to external clients using api gateway.
 - This will give us the capability to handle cross cutting concerns such as validating JWT/access token ,  Authorization and rate limiting.

## Consequences

This will solve the problem related to workflow. The workflow is related to ticket creation, ticket assigned to experts and ticket is completed at the end.


**Positive:** 

 - Handle the API security with rate limiting/throttling.
 - Handle the cross cutting concerns at one place such as access token validation , authorization.
 - This may also help in future for analytics and monetization of API incase requirement comes. 
 
**Risks:** 

 - Single point of failure
 - Configuration of the routing logic must be managed during deployment, to ensure proper routing from the external API to the proper microservice

