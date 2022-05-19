# Cluster Build

To create your cluster execute the following command:
```
/data/daffy/ocp/build.sh <your environment>
```

As a concrete example, if my environment file is called : acme-demo-env.sh then I would execute the following command:
```
/data/daffy/ocp/build.sh acme-demo
```

When you run the command you may be asked to identify which IBM Cloud account you wish to use.



provide a one-time key. Once 

```
Create ROKS Cluster
################################################################
Creation of ROKS cluster is dependent on the IBM Provider, this typical takes 30-45 minutes.
ibmcloud oc cluster create classic --name acme-demo --version 4.8_openshift --zone lon06 --flavor b3c.16x64 --hardware shared --workers 7   --public-vlan 3226246 --private-vlan 3226248 --entitlement cloud_pak
Creating cluster...
OK
Cluster created with ID ca35fmfl0ujedhu1f0rg
Waiting for cluster to be ready                                                                                  
```