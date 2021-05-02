## Tradeoffs

1. We have decided to use a Available and partitioned database in ticketing service. This is because we would need users to have quick look at the ticket either created just now or historic ones. 

It has been observed that user for sysops squad faced a lot of problem of system being unavailable and hence we went with Availability of DB as compared to consistency. Since user is anyways going to see update in few seconds this does not impact the perceived performance of the system. 

Moreover the expert assignment and visit is not a short time task so user is, we believe, ready to see some lags as compared to unavailability. Also, Availability gives user impression of system working on it(like ticket assignment) which it understands will take time.

2. To reduce the time to market and still solve the problems that plagued the most, we have went ahead with strangler pattern and not removed monolith altogether. 

We believe that this will make overall system easy to debug and at the same time performant.

3. Message queue in place of direct call to workflow service. This makes the service more agile as it can scaled independently and be deployed easily. 

Moreover this does not choke the system as their can be huge load to this service and at the same time give space for optimal usage of the resources by maintaining throughput. 

Workflow service can be choreography based and contacts monolith for expert availability. 