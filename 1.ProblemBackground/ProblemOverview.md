# Problem Overview

## Current Situation as defined

Sysops Squad - A Bad Situation…
Things have not been good with the Sysops Squad lately. The current trouble ticket system is a large monolithic application that was developed many years
ago. Customers are complaining that consultants are never showing up due to lost tickets, and often times the wrong consultant shows up to fix something
they know nothing about. Customers and call-center staff have been complaining that the system is not always available for web-based or call-based problem
ticket entry. Change is difficult and risky in this large monolith - whenever a change is made, it takes too long and something else usually breaks. Due to
reliability issues, the monolithic system frequently “freezes up” or crashes - they think it’s mostly due a spike in usage and the number of customers using the
system. If something isn’t done soon, Penultimate Electronics will be forced to abandon this very lucrative business line and fire all of the experts (including
you, the architect).
Current process in the monolithic system:
1. Sysops squad experts are added and maintained in the system through an administrator, who enters in their locale, availability, and skills.
2. Customers who have purchased the support plan can enter a problem ticket using the sysops squad website. Customer registration for the support
service is part of the system. The system bills the customer on an annual basis when their support period ends by charging their registered credit card.
3. Once a trouble ticket is entered in the system, the system then determines which sysops squad expert would be the best fit for the job based on skills,
current location, service area, and availability (free or currently on a job).
4. The sysops squad expert is then notified via a text message that they have a new ticket. Once this happens an email or SMS text message is sent to the
customer (based on their profile preference) that the expert is on their way.
5. The sysops squad expert then uses a custom mobile application on their phone to access the ticketing system to retrieve the ticket information and
location. The sysops squad expert can also access a knowledge base through the mobile app to find out what things have been done in the past to fix the
problem.
6. Once the sysops squad expert fixes the problem, they mark the ticket as “complete”. The sysops squad expert can then add information about the
problem and fix to the knowledge base.
7. After the system receives notification that the ticket is complete, the system send an email to the customer with a link to a survey which the customer then
fills out.


## Ticket Workflow
The ticketing workflow starts when a customer enters a problem ticket into the system, and ends when the customer completes the survey after the repair is done. This workflow is outlined as follows:
1. Customers who have purchased the support plan enter a problem ticket using the Sysops Squad website.
2. Once a problem ticket is entered in the system, the system then determines which Sysops Squad expert would be the best fit for the job based on skills, cur‐ rent location, service area, and availability (free or currently on a job).
3. Once assigned, the problem ticket is uploaded to a dedicated custom mobile app on the Sysops Squad expert’s mobile device. The expert is also notified via a text message that they have a new problem ticket. The customer is notified through an SMS text message or email (based on theirprofile preference) that the expert is on their way.
4. The expert uses the custom mobile application on their phone to retrieve the ticket information and location. The sysops squad expert can also access aknowledge base through the mobile app to find out what things have been done in the past to fix the problem.
5. Once the expert fixes the problem, they mark the ticket as “complete”. Thesysops squad expert can then add information about the problem and repair information to the knowledge base.
6. After the system receives notification that the ticket is complete, the system sendan email to the customer with a link to a survey which the customer then fills out.
7. The system receives the completed survey from the customer and records thesurvey information.

## Existing Architecture Component
<img src="https://user-images.githubusercontent.com/1282526/116562981-d8bfc100-a92d-11eb-9588-811c65b9949a.png" alt="arch-cmp" width="400"/>

## Existing Database Design
<img src="https://user-images.githubusercontent.com/1282526/116563180-fc830700-a92d-11eb-84d4-3efc47c0b23b.png" alt="arch-cmp" width="500"/>


## Non Ticket Workflow
The manager keeps track of problem ticket operations and receives operational and analytical reports about the overall Sysops Squad problem ticket system.
1. Sysops Squad experts are added and maintained in the system through an administrator, who enters in their locale, availability, and skills.
2. Customers register with the Sysops Squad system and have multiple support plans based on the products they purchased.
3. Customers are automatically billed monthly based on credit card information contained in their profile. Customers can view billing history and statements through the system.
4. Managers request and receive various operational and analytical reports, including financial reports, expert performance reports, and ticketing reports.
