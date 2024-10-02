---
up: 
tags:
  - kubernetes
URL: https://kubernetes.io/docs/concepts/workloads/pods/disruptions/#pod-disruption-budgets
---
Pod Disruption Budgets is a Kubernetes feature that limits the number of
[[+/Voluntary Disruptions]] that can happen to a set of pods in a specific
timeframe. 

PDBs ensure that a minimum number of replicas for a specific application
remains available during these disruptions, helping maintain high
availability.

To create a Pod Disruption Budget, you need to define a PDB resource in
your Kubernetes cluster, specifying the label selector to match the pods
and the minimum number of available pods during the disruption.

Example: 

```yaml apiVersion: policy/v1beta1 kind: PodDisruptionBudget
metadata: name: my-pdb spec: minAvailable: 2 selector: matchLabels: app:
my-app

```

