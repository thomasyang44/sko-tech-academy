# Daffy - CP4BA Deployment 

As part of the pre-work you created a bastion server, installed Daffy and created a daffy environment file. Before 
we create the cluster please update your daffy environment by running the install command again :
```commandline
wget http://get.daffy-installer.com/download-scripts/daffy-init.sh; chmod 777 daffy-init.sh;./daffy-init.sh
```
This environment file needs to be updated before Daffy can deploy the CP4BA cluster.

Login to your bastion server and update the environment file you created using the sample below as a template.

Here is a sample environment file:
```
#No spaces and only AlphaNumeric and  @ or . or -
DAFFY_UNIQUE_ID="<your email>" 

#OpenShift Cluster info
#####################################
CLUSTER_NAME="<cluster name : daffy-firstname-lastname>"
OCP_INSTALL_TYPE="roks-msp"
DAFFY_DEPLOYMENT_TYPE=Enablement

###### This only works in the itztsglenablement01, this is the account used for Tech Academy
IBMCLOUD_RESOURCE_GROUP=TechAcademyBA

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
CP4BA_DEPLOYMENT_STARTER_SERVICE_SAMPLE=roks-starter-all-IF008.yaml
CP4BA_ENABLE_SERVICE_OPS=true

#Overrides
#ROKS Platform
#    Zone that ROKS will be installed
#     https://cloud.ibm.com/docs/containers?topic=containers-regions-and-zones
ROKS_ZONE=<datacenter zone>

#####################################
OCP_CREATE_NFS_STORAGE=true
CP4BA_AUTO_STORAGE_CLASS_FAST_ROKS=managed-nfs-storage
CP4BA_AUTO_STORAGE_CLASS_OCP=managed-nfs-storage
CP4BA_AUTO_STORAGE_CLASS_OCP_BLOCK=managed-nfs-storage
CP4BA_AUTO_STORAGE_CLASS_OCP_SLOW=managed-nfs-storage
CP4BA_AUTO_STORAGE_CLASS_OCP_MEDIUM=managed-nfs-storage
CP4BA_AUTO_STORAGE_CLASS_OCP_FAST=managed-nfs-storage
```

Copy the contents of this file into the Daffy environment file on your bastion server and update the three 
placeholders < > for email, cluster and datacenter. Choose a datacenter in your region and make sure it is one 
of the following:

| US | EMEA | AP |
|:--:|:----:|:----:|
| dal13 | lon02 | tbc |
| wdc04 | lon06 | tbc |
| sjc03 | ams03 | tbc |

Please name your clusters `daffy-yourfirstname-yourlastname` eg. `daffy-tom-cruise`. This is so we can find them easily.

Daffy will deploy CP4BA and other CloudPaks using a CR yaml file (also known as a Custom Resource file) that 
specifies exactly what to install. These yaml CR are not part of Daffy itself, they can be customised and will evolve.
The CR that installs the CP4BA in this exercise is located here :

```commandline
/data/daffy/cp4ba/templates/services/samples/roks-starter-all-IF008.yaml
```

The CP4BA environment created from this CR will contain the major components of CP4BA, look in the yaml file to see
exactly what is installed. The CR we'll be using later in the Tech Academy is very similar to this sample, the only
difference is to enable communication to the Tech Zone RPA environment (these details will be described in the FAQ for 
those interested)

Once you have updated your environment file, save it and exit the editor. Proceed to the next step [Cluster Build](cluster.md)