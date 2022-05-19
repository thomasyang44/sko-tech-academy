---
title: Automation Decision Service summary
description: Automation Decision Service summary
---

<InlineNotification kind="warning">
<strong>Updated 10/22/2020</strong> - Work in progress
</InlineNotification>

## Introduction

[Decision management](https://www.ibm.com/automation/business-rules) supports three main use cases:

* Let users model, author and validate decisions in a low-code environment.
* Externalize decision logic from microservice code so it can be developed, managed and tested by business users, but still integrated as a service in a cloud native microservice based.
* Integrate with AI model for combining predictive scoring and business rules 

The [product documentation](https://www.ibm.com/support/knowledgecenter/en/SSYHZ8_20.0.x/com.ibm.dba.aid/topics/con_aid_intro.html)

## Getting started

### Installing on IBM Cloud Openshift cluster

This section is a quick summary of the steps to do to deploy version 2020.2.

##### Pre-requisites

Access to an Opendhift cluster and get `oc` CLI.

##### Get access to the container images

* Get your product entitlement key at https://myibm.ibm.com/products-services/containerlibrary site.
* If not done already create an openShift project to host the decision service

 ```shell
 oc -new-project cp4automation
 ```

* Create an image pull secret to access the IBM image registry 

 ```shell
 oc create secret docker-registry admin.registrykey --docker-username=cp --docker-password=<Generated-Key> --docker-server=cp.icr.io -n cp4automation
 > secret/admin.registrykey created
 ```

* Check that you can access and download the Cloud Pak for Automation images: 

 ```shell
 docker login cp.icr.io -u cp -p <Generated-Key>
 docker pull cp.icr.io/cp/cp4a/aae/dba-dbcompatibility-initcontainer:20.0.2
 ```

##### Install common services

* Get scripts and config files archive from IBM github cloud pak for automation: 

 ```shell
 wget https://github.com/icp4a/cert-kubernetes/archive/20.0.2.1.tar.gz
 ```

*Those scripts define custom resource definitions for kubernetes deployment.*

* Expand archive: `tar xvf 20.0.2.tar.gz`
* Change to folder cert-kubernetes-20.0.2
* If not already present on the cluster create the `common-service` OpenShift project

 ```shell
 # verify project does not exist
 oc new-project common-service
 ```
* In common-service project, run the following script to install the different operators. If you do want to set the trace of the execution, you can uncomment the second line `set -x` in this script.

  ```shell
  ./scripts/deploy_CS3.4.sh nonbai
  ```
    

##### Prepare the operator storage

* Edit `descriptors/operator-shared-pvc.yaml` and use ibmc-file-retain-gold-gid
* Create the PVC: 

 ```shell
 oc create -f descriptors/operator-shared-pvc.yaml
 ```

* Copy the drivers: 

 ```
 oc cp scripts/jdbc cp4a/<operator-podname>:/opt/ansible/share -c ansible
 ```

##### Install the operator

* Deploy operator: 

 ```
 ./scripts/deployOperator.sh -i cp.icr.io/cp/cp4a/icp4a-operator:20.0.2 -p admin.registrykey -n cp4a -a accept`
 ```

##### Deploy ODM

* Apply the CR:   (note: this CR also includes a simple install of BAI)
* Update the network policies for ODM: 

 ```
 oc get netpol
 ```

* Edit the odm-dc-networkpolicy, odm-dr-network-policy, odm-ds-console-network-policy, odm-ds-runtime-network-policy to add a blanket egress policy, for example:

 ```yaml
  spec:
  egress:
  - {}
  ingress:
  - ports:
    - port: <PORT>
      protocol: TCP
  podSelector:
    matchLabels:
      run: ppe-odm-decisioncenter
  policyTypes:
  - Egress
  - Ingress
 ```


