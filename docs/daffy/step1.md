<a name="Step1"></a>
    
**What is a bastion server? Why does it exist?**  
A bastion host is a server whose purpose is to provide access to a private network from an external network, such as the Internet. Because of its exposure to potential attack, a bastion host must minimize the chances of penetration. Openshift uses a bastion to help create a running cluster. A bastion can be reused for multiple clusters. In some scenarios for POC purposes such as User Provisioned Infrastructure (UPI), the bastion can be used as the proxy to the cluster.  

Bastion servers can be installed anywhere. This guide assumes the bastion server is Ubuntu 20.04 Minimal and will be in the IBM Cloud.  

Requirements for completing this task is to have an IBMid, an IBM cloud account, and a local SSH key. For more information, go to Daffy Prerequisites.  

Detailed below are the instructions to build your own bastion to do an IPI or MSP install.  


!!! note "If you do not have a bastion, select one of the options below."

    === "IBM Cloud Bastion"
   
    === "IBM Technology Zone Bastion"

[Go to top of section](#Step1) | [Go to top of page](#DaffyCoreSteps)
