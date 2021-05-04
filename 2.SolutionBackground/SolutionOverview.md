# Solution Overview

## Principles
- Scalability
- Feature Extensibility
- Simplicity
- Measurements and monitoring


## Transition from Monolith to Microservice Model

In accordance with our priciples, we sought for microservices design architecture. This will allow for more flexibility to add new features and horizontal scalability.

For simplicity, we are keeping the non-problematic components in monolith itself until we move completely to microservice model. This means the transition towards microservice will happen incrementally using Strangular pattern.

We also strive for little code change. for this to happend we try to use most monoliths codes, packages, logic and data schema. Implementing a modifier/adapter layer to facilitate interaction with other microservices.

To measure the load on the system and boost the performance in recent future, we also focus on measurementns and monitoring.


## Conceptual Models

Conceptual models for green field project for Sysops Squad requirement:

![domain_model](../img/domain_model.png)


## Mapping table to re-use existing components for future models
| New domain              | Existing Components                      | Existing Namespace                                | Existing table to be migrated|
|-------------------------|------------------------------------------|---------------------------------------------------|------------------------------|
| Customer Service        | Customer profile Support contract        | ss.customer.profile, ss.customer.notification     | Customer, Customer_notification
| Product Service         | Products, KB maint KB Search             | ss.kb.maintenace ss.kb.search                     | Article, Tag, Keyword, Article_Tag, Article_Keyword
| Expert Service          | Expert profile                           | ss.exprt.profile                                  | Expert_Profile, Expertise, Location
| Ticketing Service       | Ticket                                   | ss.ticket                                         | Ticket, Ticket_Type, Ticket_History
| Admin Service           | User maintenance                         | ss.users                                          |SysOps_User, Profile
| Payment Service         | Billing payment Billing history          | ss.billing.payment ss.billing.history, ss.supportcontract| Payment,Payment_method, Billing, Contract
| Survey Service          | Survey Survey Templates Survey notify    | ss.survey ss.survey.templates ss.survey.notify    | Survery, Surver_Question, Customer_Surver_Question, Customer_Survey_respondse
| Auth Service            | Login                                    | ss.login                                          | 
| Reporting Service       | Reporting                                | ss.reporting                                      |
| Ticket Workflow Service | Ticket assign Ticket notify Ticket route | ss.ticket.assign ss.ticket.notify ss.ticket.route |
| SysOps Frontend-UI      | User Interface                           |                                                   |
| Notification Service    |                    |                          |


