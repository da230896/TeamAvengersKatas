# Record architecture decisions

## Topic

<b>Deployment Strategy</b>

Date: 2021-05-03


## Status

Accepted

## Context and Problem Statement

Existing Sysops squad monolithic applictaion is having problems related to ,

- Deploybility - Takes longer time to release any feature.
- Testability - Afraid of breaking core functionality while making incremental releases.

We plan to address the above problems by leveraging continious integration and continious delivery toold while building new sys ops system 

## Considered options

- Multiple Service Instances per Host (Physical or VM)
- Service Instance Per Host (Physical or VM)
- *Service Instance per Container*
- Server-less Deployment


## Decision

In this model, each specific service instance operates in its corresponding container preferably docker engine. In this pattern, we can run several microservices containers on a physical or virtual host. For container management cluster managers such as Kubernetes will be used. 
Existing monolthic will be packed as one docker container and will be deployed alongwith strangler micro services container.
We will be using Horizontal Pod Autoscaler feature to increase the replica count by observing CPU and memory usage of the existing pod.
*Feature toggles* will be baked in from the start which will allow us to deploy frequently and get faster feedback.
Deployment into production and staging is manually initiated, all other environment builds and deployment are initiated by a commit into a branch.
Lot of focus will be given automation of unit test , smoke tests , integration tests , service tests and external contract tests (PACT).
This will give lot of confidence while making frequent release on the production.
The aim is to increae the release cadence than the existing sysop applictaion. Changes are small, with multiple small deployments a day rather than massive "releases". We then use feature toggles to enable functionality in production.


## Consequences

Each module is small and self contained. This has allowed a rapid release cycle, with pipelines driving the deployment into live. 


**Positive:** 

 - Faster time to market. Reduce Lead time for feature delivery.
 - Automation test suite will increase confidence in delivery.
 - Running multiple containerized services will ensure efficient usage of host system. 
 




