# Ansible On-Premise NVIDIA GPU Operator Deployment on disconnected Openshift.

This repository contains Ansible roles and playbooks to install, upgrade, and manage OpenShift clusters.

The openshift-ansible repository now mainly provides playbooks necessary for scaling up or upgrading RHEL hosts in existing 4.x clusters.

 The NVIDIA GPU Operator manages NVIDIA GPU resources within an OpenShift cluster and automates tasks required when preparing nodes for GPU workloads.

deploying operators in OpenShift 4.x environments.

Declarative Approach: By using kubernetes.core.k8s, the playbooks follow a more declarative pattern, aligning with Kubernetes resource management practices.

This kustomization uses [NVIDIA GPU Operator](https://github.com/NVIDIA/gpu-operator).

## Prerequisites

The OpenShift oc CLI tool is installed and logged in.
 
 Ansible is installed and configured.

 The control node has sufficient permissions to apply manifests to the OpenShift cluster.


The control node has sufficient permissions to apply manifests to the OpenShift cluster.

Ensure that you have the necessary permissions and that the OpenShift Python client is installed on the machine running these playbooks.

Install the kubernetes.core Ansible collection.


## Simple Installation

sudo ansible-playbook -i inventory/hosts.localhost playbooks/nfd-instance/nfd_instance.yml


## Deploying Node Feature Discovery Operator

OpenShift Integration: Leverage OpenShift's MachineConfig and secret management to handle sensitive configurations securely.

Deploy NFD operator using the command:

```
$ oc apply --kustomize nfd-operator/base
```

