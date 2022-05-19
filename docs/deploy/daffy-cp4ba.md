# Daffy - CP4BA Deployment 

As part of the pre-work you created a bastion server, installed Daffy and created a daffy environment file. 
This environment file needs to be updated before Daffy can deploy the CP4BA cluster.

Login to your bastion server and update the environment file you created using the sample below as a template.

Here is a sample environment file:
```
#No spaces and only AlphaNumeric and  @ or . or -
DAFFY_UNIQUE_ID="<your email>" 

#OpenShift Cluster info
#####################################
CLUSTER_NAME="<cluster name to be created>"
OCP_INSTALL_TYPE="roks-msp"

# Version must match support version of ROKS only
OCP_RELEASE="4.8.36"

# Supported VM_TSHIRT_SIZE values: Large, Min
#    Large - 6 Worker Nodes
#    Min   - 3 Worker Nodes
VM_TSHIRT_SIZE="Large"
VM_NUMBER_OF_WORKERS_LARGE=7

CP4BA_VERSION="21.0.3"
CP4BA_IFIX=IF008
CP4BA_DEPLOYMENT_STARTER_SERVICE=samples
CP4BA_DEPLOYMENT_STARTER_SERVICE_SAMPLE=roks-starter-all-IF008
CP4BA_ENABLE_SERVICE_OPS=true

#Overrides
#ROKS Platform
#    Zone that ROKS will be installed
#     https://cloud.ibm.com/docs/containers?topic=containers-regions-and-zones
ROKS_ZONE=<datacenter zone>
```
Copy the contents of this file into the Daffy environment file on your bastion server and update the three 
placeholders < > for email, cluster and datacenter. Choose a datacenter in your region and make sure it is one 
of the following:

| US | EMEA | AP |
|:--:|:----:|:----:|
| dal13 | lon02 | tbc |
| wdc04 | lon06 | tbc |
| sjc03 | ams03 | tbc |

Once you have updated your environment file, save it and exit the editor. Proceed to the next step [Cluster Build](cluster.md)