# Deployment Overview

Daffy (Deployment Automation Framework For You) makes it easy to create pre-configured CP4BA clusters. Daffy takes care of creating the OpenShift cluster and installing the CP4BA software. Once the installation is complete you'll have a new CP4BA cluster with the following components installed:

| Component                                                      |
| :------------------------------------------------------------- |
| [IBM Cloud Platform Foundation](https://www.ibm.com/docs/en/cloud-paks/cp-biz-automation/21.0.3?topic=software-cloud-platform-foundation) |
| [IBM Automation Decision Services](https://www.ibm.com/docs/en/cloud-paks/cp-biz-automation/21.0.3?topic=software-automation-decision-services) |
| [IBM Automation Document Processing](https://www.ibm.com/docs/en/cloud-paks/cp-biz-automation/21.0.3?topic=software-automation-document-processing) |
| [IBM Business Automation Application](https://www.ibm.com/docs/en/cloud-paks/cp-biz-automation/21.0.3?topic=software-business-automation-application) |
| [IBM Business Automation Workflow](https://www.ibm.com/docs/en/cloud-paks/cp-biz-automation/21.0.3?topic=software-business-automation-workflow) |
| [IBM Automation Workstream Services](https://www.ibm.com/docs/en/cloud-paks/cp-biz-automation/21.0.3?topic=software-automation-workstream-services) |
| [IBM FileNet Content Manager](https://www.ibm.com/docs/en/cloud-paks/cp-biz-automation/21.0.3?topic=software-filenet-content-manager) |
| [IBM Operational Decision Manager](https://www.ibm.com/docs/en/cloud-paks/cp-biz-automation/21.0.3?topic=software-operational-decision-manager) |

The Daffy installation is driven by the environment file that tells Daffy what type of infrastructure is being used and
what to deploy. During this Tech Academy we'll be using Daffy to install a cp4b-starter template on OpenShift running
in IBM Cloud, but you could also use Daffy to install CP4D on AWS or CP4I on Azure.

For more details on Daffy please go to the main Daffy site on W3
[Daffy on W3](https://w3.ibm.com/w3publisher/daffy) (IBM Only - Daffy will be available to IBM Partners Q3 2022).

To perform a CP4BA installation as part of Tech Academy you'll need to perform the following steps:

1. Update the Daffy installation and cluster environment file
2. Build the OpenShift cluster on IBM Cloud using the Daffy OCP build command
3. Install the CP4BA Operators using the Daffy Cp4BA build command
4. Create the CP4BA instance using the Daffy service command
5. Monitor the status of the installation and display URL's and credentials

These steps will be described in detail in the coming sections. Please proceed to [Daffy Environment](daffy-cp4ba.md)
