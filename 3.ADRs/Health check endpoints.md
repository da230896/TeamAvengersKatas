# Health Check Endpoints 

Date: 4th May 2021

## Status

Proposed

## Context

The sysops squad is a monolith system that will eventually be disintegrated in service based architecture. Even in the initial form, it can be split up into several services(auth, ticketing and ticket workflow service) that will have to be monitored. The system starts from few services, to reduce Time to Market, but will grow towards many services with smaller responsibility scopes and improved scalability. 

There should be a set of clear metrics and vision about health statuses of services. It includes not only consumption of hardware resources, but also information about processing user's requests.

## Decision

We have decided to keep a health check end point, one per service, that will tell the health status of the service. We will register them in the cloud dashboard that will spawn other instances if any one is down.

For future we have decided that we will pick up heart beat pattern for technical health checks. This way we can do fault detection by just opening a dashboard and not picking up service and pining them.

## Consequences

Technical checks help service managers to get immediate information about specific service in case of doubtful information.

## Risks

We need business health checks that can check health of critical scenarios. But that would make development a little difficult.


