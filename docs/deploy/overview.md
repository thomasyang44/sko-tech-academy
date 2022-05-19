# Deployment Overview

Daffy makes it easy to create pre-configured CP4BA clusters. Daffy takes care of creating the OpenShift cluster 
and installing th CP4BA software. Once the installation is complete you'll have a new CP4BA cluster with the following 
components installed:

* Business Automation Workflow
* Automation Decision Services
* Content Manager
* App Builder
* Business Performance Center

The Daffy installation is driven by the environment file that tells Daffy what type of infrastructure is being used and 
what to deploy. During this Tech Academy we'll be using Daffy to install a cp4b-starter template on OpenShift running
in IBM Cloud, but you could also use Daffy to install CP4D on AWS or CP4I on Azure.

For more details on Daffy please go to the main Daffy site on W3
[Daffy on W3](https://w3.ibm.com/w3publisher/daffy) (IBM Only).

To perform a CP4BA installation on IBM Cloud you need to perform the following steps:

1. Update the Daffy environment file
2. Build the Openshift cluster using the Daffy OCP build command
3. Install the CP4BA Operators using the Daffy Cp4BA build command
4. Create the CP4BA instance using the Daffy service command
5. Monitor the status of the installation and display URL's and credentials

These steps will be described in detail in the coming sections.