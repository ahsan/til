# Replicating masters for HA clusters
- Try to place master replicas in different zones. During a zone failure, all masters placed inside the zone will fail. To survive zone failure, also place nodes in multiple zones.
- Do not use a cluster with two master replicas. Consensus on a two-replica cluster requires both replicas running when changing persistent state. As a result, both replicas are needed and a failure of any replica turns cluster into majority failure state. A two-replica cluster is thus inferior, in terms of HA, to a single replica cluster.
-

<hr>

These notes are based on:
1. The official tutorials found on [kubernetes.io](https://kubernetes.io/docs/tasks/administer-cluster/highly-available-master/#best-practices-for-replicating-masters-for-ha-clusters)