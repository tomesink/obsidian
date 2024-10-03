---
up: 
tags:
  - kubernetes
URL: https://kubernetes.io/docs/tasks/administer-cluster/manage-resources/
---
We can assign minimal **resources** for CPU and memory which will be
guaranteed for a container.

We can also specify maximal **limit** of resources to be consumed by a
container/pod on a node.

If there is no limit for CPU, kubernetes will start throttle the CPU
usage my the pod .

If there is no limit for memory and the pod start exceeding the node
memory resources the pod is killed (there is no memory throttling).

We can schedule default resourcers and limits for pods inside a namespace
which has no limits and resources specified in their spec yaml. This is
called **Limit Range** (`kind: LimitRange`).

We can restrict total amount of resources used by all appplications in the
whole kubernetes cluster pres namespace. This is called **Resource Quota**
(`kind: ResourceQuota`).