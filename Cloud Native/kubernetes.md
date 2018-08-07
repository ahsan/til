# <center>Kubernetes</center>

## Introduction
> "Kubernetes coordinates a highly available cluster of computers that are connected to work as a single unit."

- Applications are deployed to a cluster without tying them specifically to individual machines.
- This decoupling of applications from their hosts, requires the applications to be packaged in containers.
- The cluster state is managed using *etcd*

## Types of resources in an Kubernetes cluster
### 1. Master
- master coordinates all activities in a cluster, such as scheduling applications, maintaining applications' desired state, scaling applications, and rolling out new updates
- exposes the Kubernetes API

### 2. Node
- VM or a physical computer that serves as a worker machine
- has Kubelet running on it which communicates with the master over the Kuberneters API

<center>

![](https://d33wubrfki0l68.cloudfront.net/99d9808dcbf2880a996ed50d308a186b5900cec9/40b94/docs/tutorials/kubernetes-basics/public/images/module_01_cluster.svg)
</center>

> Masters manage the cluster and the nodes are used to host the running applications.

<hr>

> These notes are based on the official tutorials found on [kubernetes.io](https://kubernetes.io/docs/tutorials/kubernetes-basics/create-cluster/cluster-intro/)