            
<a name="daffy-requirements"></a>

**What is required to use Daffy?**  
Before you can use the Daffy scripts, you must have the following.

1. You must have a SSH client on your local workstation.  
    - We highly recommend installing Termius as your SSH client.
    - The Termius installer can be found here:  [**Windows**](https://termius.com/windows){target="_blank"} or [**Mac**](https://termius.com/mac-os){target="_blank"}  (Only the Free Version is needed)
2. A Bastion Machine ([**Create Bastion Instructions**](./step1.md){target="_blank"})
    - Ubuntu 20.04 (Minimum Requirements: 2 CPU, 2GB Memory) with full root access (**VSphere-UPI**, * **-IPI** and *  **-MSP**)
    - Ubuntu 20.04 (Minimum Requirements: 60+ CPU, 128GB+ Memory) with full root access (**KVM-UPI**)
    - RHEL 8.X         (Minimum Requirements: 2 CPU, 2GB Memory) with full root access (* **-IPI** and * **-MSP**)
3. **Red Hat pull secret**
    - If you or your customer does not have a Red Hat pull secret  
        - Sign up for 60 day trail for OpenShift: [**Red Hat pull secret site**](https://sso.redhat.com/auth/realms/redhat-external/protocol/openid-connect/auth?client_id=rh-product-eval&redirect_uri=https%3A%2F%2Fwww.redhat.com%2Fwapps%2Feval%2Findex.html%3Fevaluation_id%3D1053&state=65bea41f-d86c-4132-8f2d-7e04fcb04fb1&response_mode=fragment&response_type=code&scope=openid&nonce=f02607dc-794c-4249-8318-40892596b6a4){target="_blank"}
            - **Important**: If your installing on a customer owned platform account or a on-prem customer datacenter, you MUST instruct your customer to register for a trial account and use their pull secret for the install. Do not use your own pull secret for customer engagements.
        - Sign up for [**IBM / Red Hat partner program**](https://ibm.seismic.com/Link/Content/DCblzS-G5atE21QtrT5dkC9Q){target="_blank"} <br>​​​​​​
            **NOTE**: All IBMer's are entitled to the Red Hat partner program. Your Red Hat pull secret can ONLY be used for training and demo purposes. Do not provide your personal pull secret to customers.
    - If you have a Red Hat account, you can find your existing pull secret here.
          - [**Login to Red Hat**](https://console.redhat.com/openshift/downloads){target="_blank"}
          - Scroll down the page until you see "Tokens" and download the pull secret.
    - Accessing Red Hat entitlements from your IBM Cloud Paks:  
        [**Accessing-red-hat-entitlements-from-your-cloud-paks**](https://www.ibm.com/docs/en/cloud-paks/1.0?topic=iocpc-accessing-red-hat-entitlements-from-your-cloud-paks){target="_blank"}

4. IBM Entitlement Key
    - If you need to get your own IBM entitlement key you can get [**here**](https://myibm.ibm.com/products-services/containerlibrary){target="_blank"}.
        - Copy to clipboard and save to a local file
    - If you need create one for a customer you can submit request [**here**](https://ibm.seismic.com/app#/doccenter/5477419a-9474-4c51-94af-b442e9169fab/doc/%252Fdd98c5a3df-6b7c-1d77-6f07-d12e63954c78%252FdfOTRiYmU4NTQtNWY4NC03Y2QyLWZjYWUtOGIxYmFmZjkyZThk%252CPT0%253D%252CU2VsbGVyIGVuYWJsZW1lbnQ%253D%252Flf37de4c61-502e-4996-aa5e-d81c1e6191b0//?mode=view&searchId=76d7b1d4-65bc-4d7d-98f9-fedbcd7fade9&anchorId=86762df5-468d-4f4c-909a-3c6def9866d1){target="_blank"}.
    - Customer can there own 60-day trial key [**here**](https://www.ibm.com/account/reg/us-en/signup?formid=urx-44505){target="_blank"}
    
[Top of page](#daffy-requirements)
