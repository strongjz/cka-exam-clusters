# CKA exam cluster(s) for training!

_Please note that this repository is not actively maintained!_

In [this](https://www.cncf.io/certification/tips) official CNCF document, with some tips for you who will try to do the CKA exam, there's a table of the clusters you will be using during the exam. See the table below.

Cluster | Members | CNI | Description
--- | --- | --- | ---
k8s | 1 etcd, 1 master, 2 worker | flannel |
hk8s | 1 etcd, 1 master, 2 worker | calico |
bk8s | 1 etcd, 1 master, 1 worker | flannel |
wk8s | 1 etcd, 1 master, 2 worker | flannel |
ek8s | 1 etcd, 1 master, 2 worker | flannel |
ik8s | 1 etcd, 1 master, 1 base node | loopback | Missing worker node

This repo contains some scripts to get you started with cluster number one (k8s).

_There's no real good structure no the scripts yet, sorry for the mess. You should start with `create_cluster.sh` though._

Enjoy!

## Summary

* _Heavily_ inspired by [Kubernetes The Hard Way](https://github.com/kelseyhightower/kubernetes-the-hard-way)
* External etcd one node cluster (!)
* Runs on GCE (VMs)
* As of now only the first cluster can be created
* Lacks flannel support
* tmux and start/stop helper scripts are provided
* Scalable, not trivial but a good way of learning e.g. how to add more nodes to a cluster

## Get started

_Pre-req_:
* Install gcloud
* Install kubectl
* Create a free tier account on [GCE](https://cloud.google.com/free/)
* Configure gcloud

_Create and run the cluster_:
1. Create a new directory somewhere on your local computer
2. Clone this repo
3. `cd` into the cloned repo directory
4. Run the `create_cluster.sh` script

#### Todo

* Clean-up script
* ~~Provide initial tool setup (kubectl and cfssl)~~
* Provide initial gcloud setup, installation and configuration
* Creation of GCE free tier
* `create-cluster.sh`
    * ~~Check if kubelet, gcloud and cfssl binaries are present~~
    * Add colors to the echoes
    * Refactor (ouch!)
    * Add argument to script to create different kinds of cluster (the others from the CKA exam)
    * Add a check to see if the provisioned instances are running
    before proceeding after creation
    * Add a way of continuing after this step, bootstrapping etc.
    * Support flannel and calico overlays (if possible in GCE)
* `bootstrap*.sh`
    * Add echoes with color
    * Find a way to execute them remotely
* The rest of the `*.sh` scripts




