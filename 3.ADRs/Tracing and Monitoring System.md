# Record architecture decisions

## Topic

<b>Tracing and Monitoring System</b>

Date: 2021-05-01


## Status

Accepted

## Context and Problem Statement

Tracing and monitoring is important to trace any devition that happens in workflow and this is one of the architecture characteristic for this system.

## Considered options

- Able to trace if tickets get lost or any other failure

## Decision

We plan to address the problem by providing tracing and monitoring platform. We are here opt-in for opensource solution, we can save some recurring expense here.

Choosing Grafana over other paid service like Datadog. 

Grafana: free of cost, and crunch huge amount of data used for metrics and loggings.

## Consequences

We will be able to look back into time and investigate issues occured.


**Positive:** 

 - Logging and metrics can easily be maintained
 - Free of cost
 
 **Negative:** 

 - Need to maitain by ourself, comes with extra effort

**Risks:** 

 - Might take long time to achieve our goal, as we need to implement platform by ourselves.

