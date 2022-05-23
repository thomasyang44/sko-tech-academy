# Monitor / Credentials

To monitor the creation of your services execute the following command.

```
/data/daffy/cp4ba/service.sh <your environment> --StarterStatus
```

As a concrete example, if my environment file is called : acme-demo-env.sh then I would execute the following command:

```
/data/daffy/cp4ba/service.sh acme-demo --StarterStatus
```
Example Output : 
```commandline
CP4BA Service Status
################################################################
Daffy Version                            :  v2022-05-BETA
Bastion OS                               :  ubuntu - 20.04
Platform Install Type                    :  roks-msp
OpenShift Version                        :  4.8.36
CP4BA Version                            :  21.0.3 IF008
Project/Namespace                        :  cp4ba-starter
Zen Version                              :  4.4.3 
Message 1                                :  Successful
Message 2                                :  Running reconciliation
Status Dump                              :  /data/daffy/log/cp4ba-acme-demo/cp4ba/icp4adeploy-cp4ba-status-info.yaml

CP4BA Service Status - Content
################################################################
cpeDeployment                            :  Ready
cpeJDBCDriver                            :  Ready
cpeRoute                                 :  Ready
cpeService                               :  Ready
cpeStorage                               :  Ready
cpeZenInegration                         :  Ready
graphqlDeployment                        :  Ready
graphqlRoute                             :  Ready
graphqlService                           :  Ready
graphqlStorage                           :  Ready
navigatorDeployment                      :  Ready
navigatorService                         :  Ready
navigatorStorage                         :  Ready
navigatorZenInegration                   :  Ready
```

To get the credentials for your CP4BA services execute the following command :

```
/data/daffy/cp4ba/service.sh <your environment> --StarterConsole
```

Here is a concrete example:

```
/data/daffy/cp4ba/service.sh acme-demo --StarterConsole
```

Along with sample output:

```commandline
Decision Console
################################################################
Username                                   : cp4admin
Password                                   : BQ**************e
Decision Center                            : https://cpd-cp4ba-starter.cp4ba-acme-demo-64b8809ea4bdf3ac103ec2bdb80f1d21-0000.eu-gb.containers.appdomain.cloud/odm/decisioncenter
Decision Runner                            : https://cpd-cp4ba-starter.cp4ba-acme-demo-64b8809ea4bdf3ac103ec2bdb80f1d21-0000.eu-gb.containers.appdomain.cloud/odm/DecisionRunner
Decision Server Console                    : https://cpd-cp4ba-starter.cp4ba-acme-demo-64b8809ea4bdf3ac103ec2bdb80f1d21-0000.eu-gb.containers.appdomain.cloud/odm/res
Decision Server Runtime                    : https://cpd-cp4ba-starter.cp4ba-acme-demo-64b8809ea4bdf3ac103ec2bdb80f1d21-0000.eu-gb.containers.appdomain.cloud/odm/DecisionService
```


