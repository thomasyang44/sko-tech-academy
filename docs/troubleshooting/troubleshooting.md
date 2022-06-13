

## 1. I can't find BAWTOS or cp4bausers
<a name="faq-200"></a>
??? note summary "Expand to view"
    Content including the labs are based on the IBM SWAT Client Onboarding[^1] materials which is executed on the Production pattern.  Our environment uses the Starter pattern and based on that, you may encounter some differences at certain steps.  
    <br>
    Below are some differences you should be aware of, please post to the slack channel if you encounter additional differences.  
    - BAWTOS => TARGET  
    - cp4bausers => cp4admin  
    
    [Go to top of section](#faq-200) | [Go to top of page](#overview)

[^1]:
    The Client Onboarding assets have been adapted from the
    <a href="https://github.com/IBM/cp4ba-labs/tree/main/21.0.3" target="_blank">IBM TechJam 21.0.3</a>
    materials as developed by the IBM SWAT Team  

## 1. What you need on IBM Cloud : infrastructure permissions
<a name="faq-100"></a>
??? note summary "Expand to view"
    Before you can order virtual machines and create clusters you need to convert your IBM Cloud account to a 
    Pay-As-You-Go account. This is option can be found under account settings. If you hve an IBM provided account
    your manage will need to approve this upgrade.

    [Go to top of section](#faq-100) | [Go to top of page](#overview)

## 2. Getting Help : sharing an oc login command
<a name="faq-110"></a>
??? note summary "Expand to view"
    If the software on your cluster is not working as expected you may be asked by an expert to provide a login command or 
    login token. This token allows them to log into your cluster using the CLI. To get the login token log into
    the OpenShift Web console, in the top right corner there is a drop-down, with your username as a label. 
    Click the label and a Copy Login Command link will be shown, this is highlighted in red below.

    ![oc console](./images/oc_login1.jpg)

    The next screen will display a link "Display Token". Click on this link and the page below will be displayed. Copy the 
    oc login command as highlighted in red.

    ![oc console](./images/oc_login2.jpg)
    
    [Go to top of section](#faq-110) | [Go to top of page](#overview)

## 3. Finding URLS : Most from Daffy
<a name="faq-120"></a>
??? note summary "Expand to view"
    
    You can find the common URL's for CP4BA in the cp4ba-access-info config map as shown below.  
    ![oc config map](./images/access-config-map.png)

    You can also use a Daffy command run from your bastion.  
    ```
    /data/daffy/cp4ba/service.sh <your environment> --StarterConsole
    ```
     
    [Go to top of section](#faq-120) | [Go to top of page](#overview)

## 4. Obscure URLS : BAW Process Admin
<a name="faq-130"></a>
??? note summary "Expand to view"
    ![WIP](../src/images/wip2.jpg){width="800"}     
         
    [Go to top of section](#faq-130) | [Go to top of page](#overview)

## 5. Pods : what to look for and how to restart
<a name="faq-140"></a>
??? note summary "Expand to view"
    ![WIP](../src/images/wip2.jpg){width="800"}     
         
    [Go to top of section](#faq-140) | [Go to top of page](#overview)

## 6. Resource Registry : automation service not found - republish
<a name="faq-150"></a>
??? note summary "Expand to view"
    ![WIP](../src/images/wip2.jpg){width="800"}     
         
    [Go to top of section](#faq-150) | [Go to top of page](#overview)

## 7. Resource Registry : how to find what is actually deployed
<a name="faq-160"></a>
??? note summary "Expand to view"
    ![WIP](../src/images/wip2.jpg){width="800"}     
     
    [Go to top of section](#faq-160) | [Go to top of page](#overview)

## 8. Slack groups for help
<a name="faq-170"></a>
??? note summary "Expand to view"
    ![WIP](../src/images/wip2.jpg){width="800"}     
     
    [Go to top of section](#faq-170) | [Go to top of page](#overview)

## 9. Getting More Help : Granting cluster console access
<a name="faq-180"></a>
??? note summary "Expand to view"
    ![WIP](../src/images/wip2.jpg){width="800"}     
     
    [Go to top of section](#faq-180) | [Go to top of page](#overview)

## 10. Logs : where do the different components log
<a name="faq-190"></a>
??? note summary "Expand to view"
    ![WIP](../src/images/wip2.jpg){width="800"}     

    [Go to top of section](#faq-190) | [Go to top of page](#overview)

## 11. Better logging : Using an external log service
<a name="faq-100"></a>
??? note summary "Expand to view"
    ![WIP](../src/images/wip2.jpg){width="800"}     
     
    [Go to top of section](#faq-200) | [Go to top of page](#overview)

## 12. Common faults & fixes : eg restart bastudio (edited)
<a name="faq-100"></a>
??? note summary "Expand to view"
    ![WIP](../src/images/wip2.jpg){width="800"}     
     
    [Go to top of section](#faq-200) | [Go to top of page](#overview)

## 13. Using Workflow to Orchestrate Asynchronous Long-Running RPA Tasks
??? note summary "Expand to view"
    <a href="https://ibm.box.com/v/ASYNC-RPA-INVOKE-LAB" target="_blank">Using Workflow to Orchestrate Asynchronous Long-Running RPA Tasks</a>   
     
    [Go to top of section](#faq-210) | [Go to top of page](#overview)

## 100. Solution Exports and Labs
??? note summary "Expand to view"

    [**Solution Exports**](https://github.com/thomasyang44/sko-tech-academy/tree/main/docs/client-onboarding/Solution%20Exports){target="_blank"}  
    [**Labs**](https://github.com/thomasyang44/sko-tech-academy/tree/main/docs/client-onboarding/labs){target="_blank"}  

     
    [Go to top of section](#faq-220) | [Go to top of page](#overview)
