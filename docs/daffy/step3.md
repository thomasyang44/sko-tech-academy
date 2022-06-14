<a name="Step3"></a>

This file is where you store values that will define your environment and that Daffy will use to build your environment.

Go to the samples directory:
```    
cd /data/daffy/env/samples
```

As a starting point, copy a sample environment file from the samples folder located here:  
```
/data/daffy/env/samples/<platform>-env.sh
```

For SKO Tech Academy, we will use CP4BA on the ROKS platform:
```
/data/daffy/env/samples/cp4ba-env.sh
```

You will copy the environment file and rename it using this format:
```
/data/daffy/env/<ENVIRONMENT_NAME>-env.sh
```

** Best practice is <ENVIRONMENT_NAME> is your cluster name but not required.

<br>
This command will copy the the sample file and place it in the /data/daffy/env directory (back one folder)
```
cp cp4ba-env.sh /data/daffy/env/<ENVIRONMENT_NAME>-env.sh
```

Here are the values of the file:
```
DAFFY_UNIQUE_ID="<YourID@ibm.com>"
#This is required - Values POC/Demo/Enablement/HCCX/TechZone
DAFFY_DEPLOYMENT_TYPE=""
#If POC/Demo, these are required.
#ISC number must be 18 characters
#DAFFY_ISC_NUMBER="0045h00000w1nvKAAG"
#DAFFY_CUSTOMER_NAME="Acme Customer"

BASE_DOMAIN="<YOUR.BASEDOMAIN.COM>"
CLUSTER_NAME="<ENVIRONMENT_NAME>"
OCP_RELEASE="4.8.36"
VM_TSHIRT_SIZE="Large"
```

| Property              | Description                                                      |
| :-------------------- | :--------------------------------------------------------------- |
| DAFFY_DEPLOYMENT_TYPE | Values POC/Demo/Enablement/HCCX/TechZone                         |
| DAFFY_ISC_NUMBER      | If Demo or POC, the ISC Record Number                            |
| DAFFY_CUSTOMER_NAME   | If Demo or POC, the Customer Name                                |
| BASE_DOMAIN           | Is your DNS name your cluster will use                           |
| CLUSTER_NAME          | The name you want to give your OpenShift Cluster                 |
| OCP_RELEASE           | Version of OpenShift you want to Install                         |
| VM_TSHIRT_SIZE        | Size of OpenShift Cluster, **Min** and **Large** supported today |

!!! note
    If **MSP** type install like ROKS, **BASE_DOMAIN** is not needed.


<br>
!!! success
   ℹ️ &nbsp; You are NOW ready to begin making the necessary edits to your **/data/daffy/env/<environment>-env.sh** file for a deployment of OCP to a specific platform.<br>
   &nbsp; &nbsp; &nbsp; &nbsp;
   Please proceed to the [**Deployment Overview**](../deploy/overview.md) section.

<br>

[Go to top of section](#Step3) | [Go to top of page](#DaffyCoreSteps)
