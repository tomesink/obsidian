---
up: 
tags:
  - kubernetes
---
Voluntary disruptions are those initiated by the user or the control plane, such as [[Pod Eviction]], [[scaling down]] node maintenance, cluster update or manually deleting a pod or deployment. 

Voluntary disruptions are manageable events that can be controlled and scheduled, allowing you to use features like [[Pod Disruption Budget]] to maintain high availability during these disruptions.

In contrast, involuntary disruptions are unexpected events, like hardware failures or network outages, that cannot be controlled or scheduled.