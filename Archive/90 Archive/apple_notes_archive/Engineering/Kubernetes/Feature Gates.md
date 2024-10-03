---
up: 
tags:
  - kubernetes
---
Mechanism that allows to enable or disable experimental or alpha
features during the development and testing phase. Using feature gates
does not impact the stability of the system. 

Feature gates use a key-value pair bool configuration which can be
enabled for API server, kubelet or controller manager:
`--feature-gates=FeatureName=true` 

Features may not be production ready.

A feature can be in _Alpha_, _Beta_ or _GA_ (General
Availability) stage. If in GA stage, the corresponding feature gate is
no longer needed
