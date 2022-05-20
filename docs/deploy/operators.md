# Operators

Operators automate the creation, configuration, and management of instances of Kubernetes-native applications.To install 
the CP4BA Operator execute the following command in Daffy:

```commandline
/data/daffy/cp4ba/build.sh <your environment>
```

**Take care, this build command is in a different directory to the previous command.**

As a concrete example, if my environment file is called : acme-demo-env.sh then I would execute the following command:
```
/data/daffy/cp4ba/build.sh acme-demo
```
Daffy will need your IBM entitlement key to access the CP4BA software in the IBM Container Registry. You should have 
obtained this entitlement key as part of the pre-work but you can get it here [IBM Key](https://myibm.ibm.com/products-services/containerlibrary)

 ![ibm key](./images/IBMKey.jpg)

Paste this entitlement key ino the Daffy terminal when prompted.
```commandline
Missing IBM Entitlement Key, to get your key, go here with your browser:
https://myibm.ibm.com/products-services/containerlibrary
Please enter here so we can save to your ~/.profile
IBM_ENTITLEMENT_KEY=eyJ0eXAiOiJILOCCdYpdv1hvXk...etc etc etc....
```
Daffy will store this key and restart the cluster with these credentials added :
```commandline
Updating PullSecret to add IBM Entitlement Key
################################################################
Checking to see if IBM Entitlement Key exists in cluster
Adding Your IBM Token to the existing Pull Secret
secret/pull-secret data updated

Restart ROKS Nodes
################################################################
ibmcloud oc worker reload -q  -f -c cp4ba-acme-demo  -w kube-ca3ohi4l08bq4l61f0v0-cp4baacmede-default-000001ed  
-w kube-ca3ohi4l08bq4l61f0v0-cp4baacmede-default-00000236  -w kube-ca3ohi4l08bq4l61f0v0-cp4baacmede-default-000003d2  
-w kube-ca3ohi4l08bq4l61f0v0-cp4baacmede-default-00000445  -w kube-ca3ohi4l08bq4l61f0v0-cp4baacmede-default-000005d9  
-w kube-ca3ohi4l08bq4l61f0v0-cp4baacmede-default-00000610  -w kube-ca3ohi4l08bq4l61f0v0-cp4baacmede-default-000007e4 
Waiting for ROKS nodes to be ready -  6 Min(s) so far                                                            
```

Next, Daffy will install the CP4BA Operators.
