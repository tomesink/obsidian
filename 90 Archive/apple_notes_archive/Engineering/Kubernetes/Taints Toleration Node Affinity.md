---
up: 
tags:
  - kubernetes
---
1. Taints:

Taints are attributes that you can assign to a node to repel certain
pods.  When a taint is assigned to a node, the system will not schedule
pods to that node unless the pod has a matching tolerance.  For example,
you might taint a node to prevent anything from being scheduled on it,
unless the pod tolerates the taint. This might be useful if you have a
group of nodes that you want to reserve for specific types of workloads.

2. Node Affinity: 

Node affinity is an attribute of the pod that allows
you to specify which nodes it can be scheduled on. Unlike taints,
which repel pods, node affinity attract pods to certain nodes.  For
example, you might set up a node affinity to schedule certain pods
on nodes with specific labels. This might be useful if you have some
heavy workloads that need to run on high-capacity nodes.

Therefore, the main difference is: Taints repel pods unless they have
matching tolerances and Node Affinity attracts pods to nodes with
matching labels.

By combination of taints and node affinity you ensure the right pods are
running on the right nodes and no other nodes are assigned to this
nodes.  So only the exact specified pods are running on exact specified
nodes only.