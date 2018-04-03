---
layout: bt_wiki
title: Kubernetes Overview
category: Kubernetes
draft: false
weight: 200

---

## Summary

Kubernetes is a container orchestrator. Cloudify is a general orchestrator. Kubernetes uses control loops to maintain resource states. Conversely, Cloudify uses event driven workflows to achieve desired states. Cloudify integrates with Kubernetes to orchestrate multi-tier application architectures that include containerized and non-containerized workloads.

## Integration Points

There are two integration points between Cloudify and Kubernetes: infrastructure orchestration and service orchestration.

Infrastructure orchestration is accomplished via the _Cloudify Kubernetes Provider_. Service Orchestration is accomplished via the _Cloudify Kubernetes Plugin_. These two features are mutually dependent. You can use one without using the other. However, together they enable you to use the best of both Kubernetes and Cloudify.


### Infrastructure Orchestration: Cloudify Kubernetes Provider

The _Cloudify Kubernetes Provider_ is the first integration point related to managing underlying infrastructure.

For example,

1. Deployment of a Kubernetes Cluster (via a blueprint).
1. Lifecycle management of the underlying infrastructure, such as healing and scaling of Kubernetes nodes, storage management, and service exposure.

To install Kubernetes and the Cloudify Kubernetes Provider, go to [Cloudify Kubernetes Provider]({{< relref "kubernetes/provider.md" >}})


### Service Orchestration: Cloudify Kubernetes Plugin

The "Cloudify Kubernetes Plugin" is the second integration point, which relates to Kubernetes API object orchestration.

For example,

1. Connecting Kubernetes objects to non-Kubernetes objects, such as a remote Windows service and a Kubernetes Pod.
1. Creating and deleting Kubernetes API objects, such as Pods, Deployments, etc.
1. Updating Kubernetes API objects such as migrating Pods from one Kubernetes Node to another.

To learn more, read the documentation on the [Cloudify Kubernetes Plugin]({{< relref "plugins/kubernetes.md" >}})

Or, to deploy a demo application, go to [Kubernetes Wordpress Example]({{< relref "kubernetes/wordpress.md" >}})


## Why not put everything in a container?

Some workloads can be delivered in a container, but there if often additional non-container configurations that need to be orchestrated. For example, part of an application may include a Windows service, or involve changes to some other custom hardware component.

Several organizations have legacy applications that will not be migrated to containers any time soon. These "hybrid cloud" scenarios are where Cloudify comes in to the picture to bridge the gap between the power of containers and hardware, or custom component, orchestration.

![diagram of services orchestration]({{< img "plugins/services-orch.png" >}})
