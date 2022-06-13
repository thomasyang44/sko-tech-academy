

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

## 2. What you need on IBM Cloud : infrastructure permissions
<a name="faq-100"></a>
??? note summary "Expand to view"
    Before you can order virtual machines and create clusters you need to convert your IBM Cloud account to a 
    Pay-As-You-Go account. This is option can be found under account settings. If you hve an IBM provided account
    your manage will need to approve this upgrade.

    [Go to top of section](#faq-100) | [Go to top of page](#overview)

## 3. Getting Help : sharing an oc login command
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

## 4. Finding URLS : Most from Daffy
<a name="faq-120"></a>
??? note summary "Expand to view"
    
    You can find the common URL's for CP4BA in the cp4ba-access-info config map as shown below.  
    ![oc config map](./images/access-config-map.png)

    You can also use a Daffy command run from your bastion.  
    ```
    /data/daffy/cp4ba/service.sh <your environment> --StarterConsole
    ```
     
    [Go to top of section](#faq-120) | [Go to top of page](#overview)

## 5. Obscure URLS : BAW Process Admin
<a name="faq-130"></a>
??? note summary "Expand to view"
    The URL for Process Admin is not recorded in the access configmap. To get to Process Admin create the URL using the
    template below. Find the URL labeled Cloud Pak Dashboard and use it as the basis for the Process Admin URL
    ```
    <Cloud Pak Dashboard>/bas/ProcessAdmin
    ```
         
    [Go to top of section](#faq-130) | [Go to top of page](#overview)

## 6. Pods : what to look for and how to restart
<a name="faq-140"></a>
??? note summary "Expand to view"
    In the CP4BA starter pattern many of the functional components run within the BA Studio pod. If your software is 
    not behaving as expected (infinite blue spinning wheels, cases not starting) try restarting the BA Studio pod.
    Expand workloads and select pods, filter using studio and find the running BA Stuid pod, click on the three dots
    and delete the pod. This will cause a new pod to be created, in several minutes login to CP4BA again and see if your
    fault has cleared.

    ![oc console](./images/ba-studio.png)
         
    [Go to top of section](#faq-140) | [Go to top of page](#overview)

## 7. Resource Registry : automation service not found - republish
<a name="faq-150"></a>
??? note summary "Expand to view"
    If you have published an automation service but the client apps that try to use it report an error then unpublish
    and republish the automation service and try again.
         
    [Go to top of section](#faq-150) | [Go to top of page](#overview)

## 8. Slack groups for help (IBM Only)
<a name="faq-170"></a>
??? note summary "Expand to view"
    For issues with the SWAT COB assets : #dba-swat-asset-qna
    
    For Daffy: #daffy-user-group
     
    [Go to top of section](#faq-170) | [Go to top of page](#overview)

## 9. Logs : where do the different components log
<a name="faq-190"></a>
??? note summary "Expand to view"
    To access logs from your pods :   

    ![oc console](./images/pod-logs.png)

    [Go to top of section](#faq-190) | [Go to top of page](#overview)

## 11. Better logging : Using an external log service
<a name="faq-100"></a>
??? note summary "Expand to view"
    If you are using ROKS on IBM Cloud you can attach a log aggregation service running on IBM Cloud to your CP4BA 
    cluster.

    Find the Log Analysis service in the IBM Cloud catalogue and create an instance. The lite service doesn't have
    any log retention so choose the 7 Day search option.
    ![oc console](./images/create-logging1.png)
     
    ![oc console](./images/create-logging2.png)

    You'll be taken to the logging service page in IBM Cloud, refresh the page in a couple of minutes and your logging
    service will appear.
    ![oc console](./images/create-logging3.png)

    Find your cluster and click on its name to open the cluster details page. 
    ![oc console](./images/create-logging4.png)
    
    Scroll down to the integrations area and connect to the logging service. Once conected the connect button will be
    replaced with a launch button.
    ![oc console](./images/create-logging5.png) 
    
    In your apps your log output will now flow through to the log analysis service. In this example a BAW Toolkit
    is logging info messages, see "Darth Vader" below.
    ![oc console](./images/create-logging6.png)

    The log analysis service is now receiving all logs from the cluster. Y can now filter by source, here we are 
    filtering for the bastudio pod but this isn't necessary, a global text search is still very effective.
    ![oc console](./images/create-logging7.png)

    At the bottom of the screen you can enter your search term to find the specific log output.
    ![oc console](./images/create-logging8.png)
    It is also useful to note the timestamp for the event then use "Jump To Timeframe" to find other events from
    other pods at the same timestamp for faultfinding. Log Analysis has many other features such as saved searches
    
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
