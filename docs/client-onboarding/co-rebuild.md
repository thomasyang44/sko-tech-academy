# Rebuild (Individual)

!!! note
    These labs assume that you have installed IBM Cloud Pak for Business Automation v21.0.3 on a ROKS cluster as described [here](../deploy/overview.md) and imported the Client Onboarding[^1] scenario as described [here](co-deploy-integrate.md).  

[^1]:
    The Client Onboarding assets have been adapted from the
    <a href="https://github.com/IBM/cp4ba-labs/tree/main/21.0.3" target="_blank">IBM TechJam 21.0.3</a>
    materials as developed by the IBM SWAT Team  

<br>
The labs below can be used to learn how various capabilities were configured in the Client Onboarding solution. As you already have expertise in one or more capability, **you are encouraged to select a lab for a capability that you have the LEAST experience with and/or is the most needed skill in your market.  Further, every member of the team should select a different rebuild lab for their first.**  Once the first Rebuild lab is completed, you may select additional rebuild labs or proceed to [Customization](co-customization.md).  
<br>
As you perform the lab, think and coordinate with your team members how you might be able to customize the capability to fit client PoC requirements.  
<br>
This lab is considered an individual activity as each team member should work on a separate rebuild lab.  However, all work should be done on the shared team cluster and **collaboration is highly recommended** as you build components into your customized Client Onboarding PoC demonstration (Day 4).  

!!! warning
    Please note that you may need to redeploy your application depending on the rebuild lab update.

!!! warning
    Content including the labs are based on the IBM SWAT Client Onboarding[^1] materials which are configured for the **Production** pattern.  Our environment uses the **Starter** pattern and based on that, you may encounter some differences at certain steps.  
    <br>
    Below are some differences you should be aware of, please post to the slack channel if you encounter additional differences.  
    - BAWTOS => TARGET  
    - CLOS => CONTENT  
    - cp4bausers => cp4admin  

    [^1]:
        The Client Onboarding assets have been adapted from the
        <a href="https://github.com/IBM/cp4ba-labs/tree/main/21.0.3" target="_blank">IBM TechJam 21.0.3</a>
        materials as developed by the IBM SWAT Team  

## Overview
<a name="rebuild-0"></a>
??? note summary "Expand to view"
    The table below lists all capabilities that we currently have labs for. A capability may contain one or more labs depending on the complexity.

    | Capability                                         | Approximate Duration |
    | :------------------------------------------------- | :------------------: |
    | [IBM Business Automation Application](#rebuild-1)  |      2-3 hours       |
    | [IBM Business Automation Insights](#rebuild-2)     |        1 hour        |
    | [IBM FileNet Content Manager](#rebuild-3)          |      2-4 hours       |
    | [IBM Automation Decision Services](#rebuild-4)     |       3 hours        |
    | [IBM Robotic Process Automation](#rebuild-5)       |      3-4 hours       |
    | [IBM Business Automation Workflow](#rebuild-6)     |      5-6 hours       |

    Select the links below to view:  
        - <a href="https://github.com/thomasyang44/sko-tech-academy/tree/main/docs/client-onboarding/labs" target="_blank">**Labs**</a>  
        - <a href="https://github.com/thomasyang44/sko-tech-academy/tree/main/docs/client-onboarding/Solution%20Exports" target="_blank">**Solution Exports**</a>  

    [Go to top of section](#rebuild-0) | [Go to top of page](#rebuild)


## 1. IBM Business Automation Application
<a name="rebuild-1"></a>
??? note summary "Expand to view"

    ### **Overview**
    This is a low-code capability of IBM Cloud Pak for Business Automation that let's business users leverage services built by developers in other parts of the platform such as Workflow, Decisions & Content.

    ### **Labs**

    - [**Introduction to IBM Business Automation Application**](labs/Business Automation Application/Lab Guide - Introduction to IBM Business Automation Application.pdf){target="_blank"}
    <a href="https://github.com/thomasyang44/sko-tech-academy/blob/main/docs/client-onboarding/labs/Business%20Automation%20Application/Lab%20Guide%20-%20Introduction%20to%20IBM%20Business%20Automation%20Application.pdf" target="_blank"> (View)</a>  
    This lab introduces you to the key concepts of IBM Business Automation Application including Application Designer. In this you will learn how to create toolkits, templates and applications that integrate with the Workflow, Decisions & Content capabilities of the CP4BA platform.  
    <br>
    **Approximate Duration:** 2 Hours  
    <br>

    [Go to top of section](#rebuild-1) | [Go to top of page](#rebuild)

## 2. IBM Business Automation Insights
<a name="rebuild-2"></a>
??? note summary "Expand to view"

    ### **Overview**  

    IBM Business Automation Insights (BAI) is a cloud capability to capture end to end business data (events) from Cloud Pak for Automation (CP4A) platform components to operational data store and long-term store (data lake).
    BAI provides real-time operational visibility to Business Managers via custom or pre-built set of dashboards. Custom dashboards can be built by IT (using Kibana) or business users (using Business Performance Center).
    The data collected by BAI and stored in the data lake can be used to inject AI into CP4A platform, for example it can be used to make recommendations to business managers and knowledge workers.
    Business Performance Center is a no-code monitoring application native to IBM Business Automation Insights. You can design and share dashboards in minutes that capture business data in near real time and provide real time awareness of important business activities and processes.

    ### **Labs**

    **Track 2 - Developer Role / Solution Implementation**

    - [**Build Business Performance Center Dashboards**](labs/Business Automation Insights/Lab%20Guide%20-%20Operational%20Intelligence%20-%20BAI%20-%20Build%20Business%20Performance%20Center%20Dashboard.pdf){target="_blank"}
    <a href="https://github.com/thomasyang44/sko-tech-academy/blob/main/docs/client-onboarding/labs/Business%20Automation%20Insights/Lab%20Guide%20-%20Operational%20Intelligence%20-%20BAI%20-%20Build%20Business%20Performance%20Center%20Dashboard.pdf" target="_blank"> (View)</a>  
    In the lab, you will learn how to build and use Business Performance Center dashboards to provide insights into a Client Onboarding workflow solution for line of business users.  
    <br>
    **Approximate Duration:** 1 Hour  
    <br>

    [Go to top of section](#rebuild-1) | [Go to top of page](#rebuild)

## 3. IBM FileNet Content Manager
<a name="rebuild-3"></a>
??? note summary "Expand to view"

    ### **Overview**

    IBM FileNet Content Manager is a flexible, full-featured content management solution that provides the foundation for IBM Cloud Pak® for Business Automation. In labs you will get introduced to important core concepts of FileNet Content Platform Engine and Content Services GraphQL which will enable you to use FileNet Content Platform Engine to build the information architecture for automation projects realized with Cloud Pak for Business Automation.

    !!! warning
        <span style="color:Red">ℹ️ **[SKO UPDATE]**</span> The **TechJam** labs were designed for many users on one cluster and hence used prefixed names using **usrxxx** (ex: **usrxxxClientName**) for content objects. For our event, please ignore any references to **usrxxx** (for names, symbolic links, etc.).  <br>
        For example, if you see **usrxxxClientName**, please use **ClientName**
        
        <span style="color:Red">ℹ️ **[SKO UPDATE]**</span> We will NOT use the **CLOS** object store and instead use the existing **CONTENT** object store. Expand the section below to further extend the object store to support the labs below.   

        ??? note summary "Expand to view"
            1. Log into the FileNet **Administrative Console for Content Engine** (ACCE) as **cp4admin** and select the object store named **CONTENT**.  
               Note: the entry in the access-info file will be named: **Content Platform Engine administration**  

            2. Navigate to Data Design -> Property Templates. Create the two property templates:

                | Name                  | Symbolic Name      |  Type     |
                | :-------------------- | :----------------- | :-------- |
                | **Case Reference ID** | Case_Reference_ID  | String    |
                | **Client Name**       |	Client_Name        | String    |

            3. Navigate to Data Design -> Classes. Create a new subclass of the **Folder** class with the name **SWAT Jam Case Folder** (Symbolic ID SWAT_JAM_Case_Folder).  

            4. Open the Folder class and add the two new property templates from above. Make sure you **Save** the modified folder subclass.  

            5. Create the indicated folder structure under the Root folder. The **Case Folders** folder is a regular folder using the **Folder** object class.  
            <br> The **Sample Test Folder TEST1** should be created using the **SWAT Jam Case Folder** class and have the **Case Reference ID** and **Client Name** properties set to **TEST1**.  
            <br> The **Sample Test Folder TEST2** should be created using the **SWAT Jam Case Folder** class and have the **Case Reference ID** and **Client Name** properties set to **TEST2**.  
            <br>
            ![SecuritySetupWizard](../images/co-clos-120.png){width="400"}  

            6. Open Content Navigator, select the existing **content** desktop and update the **Layout** tab and enable the **Simple Search** feature (if it is not already enabled).
            


    ### **Labs**
    
    - [**Setting up FileNet Content Manager for Automation Projects on Cloud Pak for Business Automation**](labs/Content/CONTENT%20Lab%201%20-%20CPE.pdf){target="_blank"}
    <a href="https://github.com/thomasyang44/sko-tech-academy/blob/main/docs/client-onboarding/labs/Content/CONTENT%20Lab%201%20-%20CPE.pdf" target="_blank"> (View)</a>  
        - <span style="color:Red">ℹ️ **[SKO UPDATE]**</span> Please skip **Exercise 4 - Storage** and ensure you read the info in the **Overview** section above.  
    In this lab, you will create a small hierarchy of Document classes to
    capture different kinds of documents together with custom metadata,
    and will learn about the most important security concepts. You will
    explore Document storage and learn to migrate documents between
    different Storage Areas.  Further you will determine how to trigger
    custom actions for example when new documents have arrived, and how to
    configure and test functionality of content based retrieval,
    i.e. searches for documents based on information contained in the
    documents themselves, not (only) on their metadata.
    <br><br>
    On this lab, for triggering the custom actions, a custom javascript is used to file a newly uploaded document into a folder, those identity is derived from a search. The script is available in the
    <a href="https://github.com/thomasyang44/sko-tech-academy/blob/main/docs/client-onboarding/labs/Content/Lab%20Data" target="_blank">**Lab Data**</a>
    folder.  
    <br>
    **Approximate Duration**: 4 - 5 hours  
    <br>

    - [**Interfacing FileNet Content Platform Engine with GraphQL on Cloud Pak for Business Automation**](labs/Content/CONTENT%20Lab%202%20-%20GraphQL.pdf){target="_blank"}
    <a href="https://github.com/thomasyang44/sko-tech-academy/blob/main/docs/client-onboarding/labs/Content/CONTENT%20Lab%202%20-%20GraphQL.pdf" target="_blank"> (View)</a>  
    The second lab on GraphQL builds on top of the first one, as the searches performed using GraphQL use the documents and document classes defined in the first lab. Here you learn by a series of example, how to build the most important queries using GraphQL. The examples also show how to download documents using GraphQL, how to create folders, and modify security settings.  
    <br>
    **Approximate Duration**: 1.5 - 2 hours  
    <br>

    [Go to top of section](#rebuild-1) | [Go to top of page](#rebuild)

## 4. IBM Automation Decision Services
<a name="rebuild-4"></a>
??? note summary "Expand to view"

    ## **Overview**

    Part of the IBM Cloud Pak® for Business Automation platform, IBM Automation Decision Services provides a comprehensive environment for authoring, managing, and running decision services. Business experts can infuse intelligence into business decisions by combining decision models and predictive models into decision services. Business decisions can be published as Automation Services and easily consumed from other capability of the platform such as Workflow.

    ## **Labs**

    - [**Manage Decisions and infuse Machine Learning**](labs/Decisions/Lab%20Guide%20-%20Automation%20Decision%20Services.pdf){target="_blank"}
    <a href="https://github.com/thomasyang44/sko-tech-academy/blob/main/docs/client-onboarding/labs/Decisions/Lab%20Guide%20-%20Automation%20Decision%20Services.pdf" target="_blank"> (View)</a>  
    This Lab  introduces you to the key concepts of IBM Business Automation Decision Services. It includes three exercises that can be done separately. In this Lab you learn how to model business decisions, infuse intelligence by adding a predictive model, share and publish decision services.  
    <br>
    **Approximate Duration**: 3 hours  
    <br>

    [Go to top of section](#rebuild-1) | [Go to top of page](#rebuild)

## 5. IBM Robotic Process Automation
<a name="rebuild-5"></a>
??? note summary "Expand to view"

    ## **Overview**

    Going from simple, back-office task automation to scaled  automation to handle time-consuming business processes can be a  challenge. The IBM® Robotic Process Automation offering helps you automate more business and IT processes at scale with the ease and speed of traditional RPA. Software robots, or bots, can act on AI insights to  complete tasks with no lag time and enable you to achieve digital transformation.            

    ## **Labs**

    - [**Application Automation using IBM RPA**](labs/Robotic%20Process%20Automation/Lab%20Guide%20-%20Application%20Automation%20using%20IBM%20RPA.pdf){target="_blank"}
    <a href="https://github.com/thomasyang44/sko-tech-academy/blob/main/docs/client-onboarding/labs/Robotic%20Process%20Automation/Lab%20Guide%20-%20Application%20Automation%20using%20IBM%20RPA.pdf" target="_blank"> (View)</a>  
    In this lab you will learn how to use IBM RPA Studio to develop a bot to automate a Java swing application and a web application.
    <br>

    - [**IBM RPA and Workflow Integration**](labs/Robotic%20Process%20Automation/Lab%20Guide%20-%20IBM%20RPA%20and%20Workflow%20Integration.pdf){target="_blank"}
    <a href="https://github.com/thomasyang44/sko-tech-academy/blob/main/docs/client-onboarding/labs/Robotic%20Process%20Automation/Lab%20Guide%20-%20IBM%20RPA%20and%20Workflow%20Integration.pdf" target="_blank"> (View)</a>  
    In this lab you will learn how the bot designed in RPA Studio can easily be integrated into a business process developed with the Workflow capability in IBM Cloud Pak for Business Automation.

    - [**Chatbot Development and Configuration**](labs/Robotic%20Process%20Automation/Lab%20Guide%20-%20Chatbot%20Development%20and%20Configuration.pdf){target="_blank"}
    <a href="https://github.com/thomasyang44/sko-tech-academy/blob/main/docs/client-onboarding/labs/Robotic%20Process%20Automation/Lab%20Guide%20-%20Chatbot%20Development%20and%20Configuration.pdf" target="_blank"> (View)</a>  
    In this lab you will learn how to develop a chatbot script using IBM RPA Studio, and then shows how to configure the chat mapping through web client.  
    <br>
    The labs requires an IBM RPA client environment which can be reserved
    <a href="https://techzone.ibm.com/collection/cloud-pak-for-business-automation-cp-4-ba-onboarding-rpa"
    target="_blank">**here**.</a>
    Once you have reserved an environment, you will receive a link to the environment via email. Start the environment by selecting the start button in the upper right corner of the page. Please use your license ID/password to activate RPA client as described in the lab instructions.
    <br>

    [Go to top of section](#rebuild-1) | [Go to top of page](#rebuild)

## 6. Business Automation Workflow
<a name="rebuild-6"></a>
??? note summary "Expand to view"
    ### **Overview**

    IBM Business Automation Workflow is software that combines business process management and case management  capabilities in a single integrated workflow solution. It unites information process, and users to provide a 360-degree view of work to help drive more successful business outcomes.

    !!! warning
        <span style="color:Red">ℹ️ **[SKO UPDATE]**</span> The **TechJam** labs were designed for many users on one cluster and hence used prefixed names using **UsrNNN** (ex: **UsrNNN Client Onboarding**) for naming case types.  For our event, please ignore any references to **UsrNNN** (for names, symbolic links, etc.).  
        <br>
        For example, if you see **UsrNNN Client Onboarding**, please use **Client Onboarding**

    ### **Labs**

    - [**Introduction to IBM Business Automation Workflow**](labs/Workflow/Lab%20Guide%20-%20Introduction%20to%20IBM%20Business%20Automation%20Workflow.pdf){target="_blank"}
    <a href="https://github.com/thomasyang44/sko-tech-academy/blob/main/docs/client-onboarding/labs/Workflow/Lab%20Guide%20-%20Introduction%20to%20IBM%20Business%20Automation%20Workflow.pdf" target="_blank"> (View)</a>  
    This lab showcases how you can create a sample Workflow project using Case features. It covers Case & Process integration and building UIs using Coaches.
    <br><br>
    **Approximate Duration**: 3-4 hours  
    <br>
    - [**Consume & Publish Automation Services in Workflow**](labs/Workflow/Lab%20Guide%20-%20Consume%20%26%20Publish%20Automation%20Services%20in%20Workflow.pdf){target="_blank"}
    <a href="https://github.com/thomasyang44/sko-tech-academy/blob/main/docs/client-onboarding/labs/Workflow/Lab%20Guide%20-%20Consume%20%26%20Publish%20Automation%20Services%20in%20Workflow.pdf" target="_blank"> (View)</a>  
    This lab showcases how you can consume capabilities from the IBM Automation platform using Automation Services. You will also create an external service to invoke a Java app that sends out emails. Finally, you will learn how an automation service can be published for others to consume.  
    <br>
    **Approximate Duration**: 2 hours  
    <br>

    [Go to top of section](#rebuild-1) | [Go to top of page](#rebuild)
