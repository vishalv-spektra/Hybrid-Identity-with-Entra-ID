# Getting Started with Hybrid Identity with Entra ID

#### Overall Estimated Duration: 4 Hours

## Overview

In this lab, you will explore the complete Hybrid Identity experience with Entra ID. You will work through hands-on labs designed to strengthen your organization's security posture by configuring passwordless authentication, access reviews, external collaboration, conditional access policies, monitoring, auditing, and Privileged Identity Management (PIM). You will also learn how to enable self-service password reset (SSPR) and seamlessly integrate on-premises Active Directory with Entra ID to implement a robust hybrid identity solution. 

Through guided steps and practical scenarios, this lab will equip you with the skills needed to secure and manage identities across both on-premises and cloud environments.

## Objectives

By completing this lab series, you will have comprehensive knowledge of designing, deploying, and managing a **Hybrid Identity** solution with **Microsoft Entra ID** for enterprise-scale adoption:

- Configure **Active Directory Domain Services** and synchronize on-premises AD identities with **Microsoft Entra ID** using **Entra Connect**.
- Enable **self-service password reset** with **password writeback** and validate synchronization across on-premises and cloud environments.
- Assign **Azure resource roles** with **Privileged Identity Management** using **time-bound, eligible assignments** with approval workflows.
- Create a **Log Analytics Workspace** and configure **diagnostic settings** to collect and analyze **Entra ID audit and sign-in logs**.
- Create **security groups**, configure **recurring access reviews**, and set up **external collaboration** with **guest user access controls**.

## Architecture

- **Hybrid Identity Framework** integrates on-premises Active Directory with Microsoft Entra ID to enable enterprise-scale identity management and governance. **Active Directory Domain Services (AD DS)** serves as the on-premises identity foundation, managing users, groups, and resources within the corporate network. **Microsoft Entra Connect** facilitates seamless directory synchronization between on-premises AD and Microsoft Entra ID, enabling unified identity management across cloud and on-premises environments.

- **Microsoft Entra ID** provides centralized cloud-based identity and access management, enforcing **security baselines, conditional access policies** to protect resources. **Privileged Identity Management (PIM)** manages and monitors privileged access through time-bound, approval-based role assignments, ensuring security and governance controls. **Log Analytics Workspace** and **Azure Monitor** collect and analyze audit logs, sign-in logs, and security events for compliance, threat detection, and operational insights.

- **Access Reviews** and **Role-Based Access Control (RBAC)** establish governance controls, enabling regular access validation and least-privilege permissions. **External Collaboration Settings** and **Guest User Management** facilitate secure partner and vendor access with configurable invitation and access restrictions. **Self-Service Password Reset (SSPR)** with password writeback ensures users can manage credentials securely while maintaining synchronization between cloud and on-premises environments.

## Architecture Diagram

![](../media/hybrid-identity-arch-diag-1303.png)

## Explanation of Components

- **Microsoft Entra ID:** Microsoft Entra ID is a cloud-based identity and access management service that provides single sign-on (SSO), multi-factor authentication (MFA), and conditional access capabilities. It serves as the central identity provider for cloud and hybrid environments, enabling organizations to authenticate users, manage application access, and enforce security policies across the organization.

- **Active Directory Domain Services (AD DS):** Active Directory Domain Services is the on-premises identity management system that manages users, computers, and resources within a corporate network. It provides authentication, authorization, and directory services, forming the foundation of on-premises identity infrastructure and requiring synchronization with cloud services through tools like Microsoft Entra Connect.

- **Microsoft Entra Connect:** Microsoft Entra Connect is a synchronization tool that bridges on-premises Active Directory with Microsoft Entra ID, enabling bidirectional identity synchronization. It ensures that user accounts, groups, and contacts are consistently maintained across both environments, while supporting password writeback for on-premises password changes initiated from the cloud.

- **Azure Monitor:** Azure Monitor is a comprehensive monitoring service that collects, analyzes, and visualizes telemetry data from Azure resources, applications, and on-premises systems. It enables proactive performance tracking, anomaly detection, and issue identification through metrics, logs, and traces, providing insights into system health, availability, and performance trends.

- **Azure Log Analytics:** Azure Log Analytics is a powerful tool within Azure Monitor that collects and queries logs from various Azure services, on-premises resources, and third-party sources. It provides deep insights into application health, performance, security events, and user behavior through Kusto Query Language (KQL), enabling investigation, alerting, and compliance reporting for security and operational purposes.

## Accessing Your Lab Environment

Once you are ready to dive in, your virtual machine and lab guide will be right at your fingertips within your web browser.

![](../media/intropupd.png)

### Virtual Machine & Lab Guide
 
Your virtual machine is your workhorse throughout the workshop. The lab guide is your roadmap to success.

## Exploring Your Lab Resources
 
To get a better understanding of your lab resources and credentials, navigate to the **Environment** tab.

![](../media/env-0903.png)

## Utilizing the Split Window Feature
 
For convenience, you can open the lab guide in a separate window by selecting the **Split Window** button from the Top right corner.

![](../media/introp2upd.png)
 
## Managing Your Virtual Machine
 
Feel free to **Start, Stop, or Restart (2)** your virtual machine as needed from the **Resources (1)** tab. Your experience is in your hands!

![](../media/res-0903.png)

## Lab Guide Zoom In/Zoom Out
 
To adjust the zoom level for the environment page, click the **A↕ : 100%** icon located next to the timer in the lab environment.

![](../media/zoomin.png)

## Let's Get Started with Azure Portal

1. On your Lab virtual machine, click on the **Azure Portal** icon to sign in to the Azure.

    ![](../media/signin0-0903.png) 

1. On the **Sign in** blade, you will see a login screen, in which enter the following email/username and password and then click on **Sign in**.  

   * **Azure Username/Email**:  <inject key="AzureAdUserEmail"></inject> 

        ![](../media/signin1-0903.png) 

   * **Temperory Access Pass**:  <inject key="AzureAdUserPassword"></inject>
  
        ![](../media/signin2-0903.png)
  
1. If you see the pop-up **Stay Signed in?** click **Yes**.

    ![](../media/g3.jpg)

1. If you see the pop-up **You have free Azure Advisor recommendations!** close the window to continue the lab. 

1. If a **Welcome to Microsoft Azure** popup window appears, click **Maybe Later** to skip the tour.

    ![](../media/g4.jpg)

## Support Contact

The CloudLabs support team is available 24/7, 365 days a year, via email and live chat to ensure seamless assistance at any time. We offer dedicated support channels tailored specifically for both learners and instructors, ensuring that all your needs are promptly and efficiently addressed.

Learner Support Contacts:

- Email Support: cloudlabs-support@spektrasystems.com
- Live Chat Support: https://cloudlabs.ai/labs-support

Click **Next** from the bottom right corner to embark on your Lab journey!

![](../media/up4.png)

### Happy Learning!!
