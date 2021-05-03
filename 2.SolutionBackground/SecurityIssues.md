# Risks

## Business risk

1. Notification about ticket not sent to either of the entities
    - We will keep notification via multiple channel so that notification is always received 
    - User has always the option of calling the call center and knowing the status of the ticket

2. Expert alloted to a ticket but did not show up. 
    - User contact call center and let the system record that.
    - Call center entity can update the ticket (remove the assigned expert from ticket and send it for reassignment)
    - We can have expert assignment based on rate of fulfillment

3. Ticket is stuck in process of allotting an expert
    - Monitor the ticket workflow service and its queue so that before customer contact we are already aware of issue

## Technical risk

1. UI application goes down
    - Maintaining several instances of the front end services to give high availability

2. Ticket gets lost in the system
    - We will prevent this by keeping disaster recovery and also keeping databases secure
    - While routing via queue can be resilient by mirroring

3. Monolith goes down
    - Going for micro service architecture

4. Breaking change in production
    - Keeping the older version ready in such case and hence having deployment strategies


# Sensitive Points

## Business related

1. Training of sysops squad experts since they represent the sysops squad while visiting a customer
2. Hiring of well versed call center agency since they will also impact customer perception of sysops squad
3. Content check when user or expert is entering some details in the ticket. It should not be vulgar or insulting.

## Technical

1. Scaling out at correct time
2. Monitoring and circuit breakers
