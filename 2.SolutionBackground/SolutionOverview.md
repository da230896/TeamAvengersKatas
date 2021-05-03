# Solution Overview

## Principles
- Scalability
- Feature Extensibility
- Simplicity
- Measurements and monitoring


## Transition from Monolith to Microservice Model

To accordance with our priciples, we sought for microservices design architecture. This will give the system to scale horizontally and add flexibility to add new features, since we see the growth of the lucritive business across country.

For simplicity, we are keeping the non-problematic components in monolith itself until we move completely to microservice model. This means the transition towards microservice will happen incrementally using Strangular pattern.

To measure the load on the system to boost the performance in recent future, we also focus on measurementns and monitoring.


## Conceptual Models

Conceptual models for green field project for Sysops Squad requirement:

![domain_model](../img/domain_model.png)


## Mapping table to re-use existing components for future models
| New domain              | Existing Components                      | Existing Namespace                                |
|-------------------------|------------------------------------------|---------------------------------------------------|
| Customer Service        | Customer profile Support contract        | ss.customer.profile ss.supportcontract            |
| Product Service         | KB maint KB Search                       | ss.kb.maintenace ss.kb.search                     |
| Expert Service          | Expert profile                           | ss.exprt.profile                                  |
| Notification Service    | Customer notification                    | ss.customer.notification                          |
| Ticketing Service       | Ticket                                   | ss.ticket                                         |
| Auth Service            | Login                                    | ss.login                                          |
| Payment Service         | Billing payment Billing history          | ss.billing.payment ss.billing.history             |
| Reporting Service       | Reporting                                | ss.reporting                                      |
| SysOps Frontend-UI      | User Interface                           |                                                   |
| Survey Service          | Survey Survey Templates Survey notify    | ss.survey ss.survey.templates ss.survey.notify    |
| Ticket Workflow Service | Ticket assign Ticket notify Ticket route | ss.ticket.assign ss.ticket.notify ss.ticket.route |
| Admin Service           | User maintenance                         | ss.users                                          |

