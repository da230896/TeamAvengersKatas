# Record architecture decisions

## Topic

<b>Leverage Orchestration in API Gateway for security requirement</b>

Date: 2021-05-01

## Status

Accepted

## Context and Problem Statement

For our microservices, we need somekind of orchestration or choreography for ticket workflow.

## Considered options

- easy error handling, easy to trace back reasons the lost tickets

## Decision

We decided to maintain orchestration in api gateway. This will give us the capability to solve the problem related to workflow in microservices. Our main principle here is observability.

## Consequences

This will solve the problem related to workflow. The workflow is related to ticket creation, ticket assigned to experts and ticket is completed at the end.


**Positive:** 

 - Handle the workflow and log the error. This will give us the observability for lost tickets and any other issues in the workflow.

**Risks:** 

 - Single point of failure
