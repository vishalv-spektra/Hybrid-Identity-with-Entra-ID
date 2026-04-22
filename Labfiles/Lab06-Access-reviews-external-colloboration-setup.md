# Lab 05: Configure Access reviews and external collaboration setup

#### Estimated Duration: 60 Minutes

## Overview 

This lab focuses on setting up access reviews to ensure proper management of user permissions within Microsoft Entra ID, enhancing security and compliance. By creating groups and configuring access reviews, administrators can regularly monitor and adjust user access to Teams and Groups, optimizing resource allocation while minimizing security risks.

## Objectives

In this lab, you will perform the following:
- Exercise 1: Configure Access reviews
  - Task 1: Create a group
  - Task 2: Configure access review
  - Task 3: Review access to groups and applications in access reviews
- Exercise 2: Configure external collaboration settings
  - Task 1: Enable Guest Users to perform self service sign-up
  - Task 2: Configure external collaboration settings

## Exercise 1: Configure Access reviews

### Task 1: Create a group

In this task, you will create a Microsoft 365 group named **All Users** in the Azure portal, assign ODL_User as the owner, and add specified members to the group.

1. On the **Azure portal**, search **(1)** and navigate to **Microsoft Entra ID (2)**

   ![](../media/L5E1T1S1-0903.png)

1. Select **Groups** under **Manage**

   ![](../media/L5E1T1S2-0903.png)

1. Select **All Groups (1)** and click on **+ New group (2)**

   ![](../media/L5E1T1S3-0903.png)

1. Create a group based on the below settings

   | Setting | Value |
   |----------|--------|
   | Group type | **Microsoft 365 (1)**|
   | Group name | **All Users (2)** |
   | Group description | **Similar access group (3)** |
   | Microsoft Entra roles can be assigned to the group | **Yes (4)** |
   | Owners | Click on **no owners selected** and select **ODL_User <inject key="DeploymentID" enableCopy="false"/>** (**5)** from the list |
   | Members | Click on **no members selected** and select **Allan**, **Joni**, **Mirinda**, **Edmund** and also include **ODL_User <inject key="DeploymentID" enableCopy="false"/>** **(6)** from the list |

      ![](../media/L5E1T1S4-0903.png)

1. Click on **Create (7)** and select **Yes**
   
   > **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps
   > - Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
   > - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
   > - If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help you out.

   <validation step="fa844ca4-5958-40e0-a9f4-e3bd09e13380" />

### Task 2: Configure access review

In this task, you will configure an access review in Microsoft Entra ID to review access permissions for Teams and Groups. The access review will include all users and will recur monthly. Reviewers will be selected from a specific user group, and notifications will be sent to all users at the end of the review. The review will auto-apply results to resources and take recommendations if reviewers don't respond. Ensure the settings are accurate before creating the access review.

1. Navigate back to Overview page of **Microsoft Entra ID** then select **Identity governance** under **Manage** section .

   ![](../media/L5E1T2S1-0903.png)

1. From the left navigation pane expand **(1)** and select **Access reviews (2)** and select **+ New access review (3)**.

   ![](../media/L5E1T2S2-0903.png)

1. On the **Choose an Access Review Template**, select **Review access to a resource type**

   ![](../media/L5E1T2S3-0903.png)

1. On **New access review** page, provide the below settings and Select **Next:Reviews (7)**.

   - Select what to review: **Teams + Groups (1)**
   - Review scope: **Select Teams + Groups (2)**
   - Group: Click on **+ Select groups (3)**
   - Select the group **All Users (4)** that you created in the previous task and click on **Select (5)**.
   - Scope: **All users (6)**

      ![](../media/L5E1T2S4.1-0903.png)

      ![](../media/L5E1T2S4.2-0903.png)

1. On **Reviews** tab enter the following and click on select **Next: Settings (4)**

   - Select reviewers: **Selected user(s) or group(s) (1)**
   - Users or Groups: Click **+ Select Reviewers** and select **ODL_User <inject key="DeploymentID" enableCopy="false"/> (2)** from the list.
   - Review recurrence: **Monthly (3)**

      ![](../media/L5E1T2S5-0903.png)

1. On the **Settings** tab enter the following and select **Next: Review + Create (4)**

   - Auto apply results to resource: **Check (1)**
   - If reviewers don't respond: **Take recommendations (2)**
   - At the end of review, send notifications to: Click **+ Select User(s) or Group(s)** and select **ODL_User <inject key="DeploymentID" enableCopy="false"/> (3)**

      ![](../media/new1-5-4.png)

1.  On the **Review + Create** tab enter **AccessreviewforAllusers** to the **Review name** and click **Create**.

     ![](../media/new1-5-5.png)

1. Wait for the access review status to become Active before proceeding to the next task. You can refresh the page to see the updated status.

     ![](../media/L5E1T2S8-0903.png)

   > **Note:** It may take a few minutes for the access review to become active. 

### Task 3: Review access to groups and applications in access reviews

In this task, you will review and manage user access to groups and applications through access reviews in the My Access portal. You will either manually assess and decide on user access or accept system-generated recommendations for managing permissions efficiently.

1. Open a new InPrivate window in Microsoft Edge and navigate to My Access using the below URL: 

   ```
   https://myaccess.microsoft.com/
   ```

1. Sign in using the ODL_User credentials.

   - Username : **<inject key="AzureAdUserEmail"></inject>**
   - Password : **<inject key="AzureAdUserPassword"></inject>**   

1. Select **Access reviews (1)** from the left menu to see a list of pending access reviews assigned to you **(2)**.

   ![](../media/L5E1T3S2-0903.png)

1. After you open My Access under Groups and Apps, you can see:

      * **Name**: The name of the access review.
      * **Due**: The due date for the review. After this date, denied users could be removed from the group or app being reviewed.
      * **Resource**: The name of the resource under review.
      * **Progress**: The number of users reviewed over the total number of users part of this access review.

1. Select the name of the  access review that you created to get started.

1. After it opens, you will see the users in the scope for the access review.

1. There are two ways that you can approve or deny access:

    - You can manually approve or deny access for one or more users.
    - You can accept the system recommendations.

1. **Manually review access for one or more users** - follow the below steps

    - Review the list of users and decide whether to approve or deny their continued access.

    - Select one or more users by selecting the circle next to their names.

    - Select Approve or Deny on the bar.

    - If you're unsure if a user should continue to have access, you can select Don't know. The user gets to keep their access, and your choice is recorded in the audit logs. Keep in mind that any information you provide is available to other reviewers. They can read your comments and take them into account when they review the request.

    - The administrator of the access review might require you to supply a reason for your decision in the Reason box, even when a reason isn't required. You can still provide a reason for your decision. The information that you include is available to other approvers for review.

     - Select Submit.

    - You can change your response at any time until the access review has ended. If you want to change your response, select the row and update the response. For example, you can approve a previously denied user or deny a previously approved user.

      ![](../media/L5E1T3S8-0903.png)

1. **Review access based on recommendations** - Follow the below steps

    -  Click on **Details** next to the access review.
     
    - To make access reviews easier and faster for you, Azure provides recommendations that you can accept with a single selection. There are two ways that the system generates recommendations for the reviewer. One method is by the user's sign-in activity. If a user has been inactive for 30 days or more, the system recommends that the reviewer deny access.

    - The other method is based on the access that the user's peers have. If the user doesn't have the same access as their peers, the system recommends that the reviewer deny that user access.

    - If you have No sign-in within 30 days or Peer outlier enabled, follow these steps to accept recommendations:

    - Select one or more users, and then select Accept recommendations Or to accept recommendations for all unreviewed users, make sure that no users are selected and then select the Accept recommendations button on the top bar.

    - Select Submit to accept the recommendations.

      ![](../media/L5E1T3S9-0903.png)

## Exercise 2: Configure external collaboration settings

### Task 1 - Enable Guest Users to perform self service sign-up

In this task, you will configure settings to allow guest users to sign up for access on their own in Microsoft Entra by enabling the self-service sign-up feature.

1. Open a browser tab to sign in to the Microsoft Entra Admin Center using the below URL:

   ```
   https://entra.microsoft.com
   ```

1. Sign in using the ODL credentials:

   - Username: <inject key="AzureAdUserEmail"></inject> 
   - Password: <inject key="AzureAdUserPassword"></inject>

1. Select **Users (1)** under **Entra ID**.

1. Select **User Settings (2)** then scroll down and select **Manage external user collaboration settings (3)**.
   
    ![](../media/L5E2T1S4-0903.png)

1. Select **Yes (1)** for the setting Enable guest self-service sign up via user flows and then click on **Save (2)** at the top of the screen.

    ![](../media/L5E2T1S5-0903.png)

### Task 2 - Configure external collaboration settings

In this task, you will configure external collaboration settings by enabling email one-time passcode notifications, setting guest user access levels, specifying who can invite guest users, and configuring collaboration restrictions.

1. From the left navigation pane, under **Entra ID** select **External Identities (1)**, and then select **All identity providers (2)**.

1. Select the **Email one-time passcode (3)** configured link.

   ![](../media/L5E2T2S1-0903.png)

   >**Note:** A one-time passcode is a very secure way to invite a user to join your organization.

1. Ensure that **Yes** is selected. If not, select **Yes** to enable email one-time passcode for guest users and then click on **Save**.

1. Select **External Collaboration Settings** on the left navigation pane.

1. Under **Guest user access**, review access levels that are available and then select **Guest user access is restricted to properties and memberships of their own directory objects (most restrictive)**.

   >**NOTE:**

      - Guest users have the same access as members (most inclusive): This option gives guests the same access to Microsoft Entra resources and directory data as member users.
      - Guest users have limited access to properties and memberships of directory objects: (Default) This setting blocks guests from certain directory tasks, like enumerating users, groups, or other directory resources. Guests can see membership of all non-hidden groups.
      - Guest user access is restricted to properties and memberships of their own directory objects (most restrictive): With this setting, guests can access only their own profiles. Guests are not allowed to see other users’ profiles, groups, or group memberships.Screen image displaying guest user access restriction options

        ![](../media/new1-5-9.png)

1. Under **Guest invite settings**, select **Member users and users assigned to specific admin roles can invite guest users including guests with member permissions!**

   >**NOTE:**

      - Anyone in the organization can invite guest users including guests and non-admins (most inclusive): To allow guests in the organization to invite other guests including those who are not members of an organization, select this radio button.
      - Member users and users assigned to specific admin roles can invite guest users including guests with member permissions: To allow member users and users who have specific administrator roles to invite guests, select this radio button.
      - Only users assigned to specific admin roles can invite guest users: To allow only those users with administrator roles to invite guests, select this radio button. The administrator roles include Global Administrator, User Administrator, and Guest Inviter.
      - No one in the organization can invite guest users including admins (most restrictive): To deny everyone in the organization from inviting guests, select this radio button.
      - If Members can invite is set to No and Admins and users in the guest inviter role can invite is set to Yes, users in the Guest Inviter role will still be able to invite guests.

        ![](../media/new1-5-10.png)
        
1. Under **Collaboration restrictions**, review the available options and accept the default settings.

    >**IMPORTANT**

      - You can create either an allow list or a deny list. You can’t set up both types of lists. By default, whatever domains are not in the allow list are on the deny list, and vice versa.
      - You can create only one policy per organisation. You can update the policy to include more domains, or you can delete the policy to create a new one.
      - The number of domains you can add to an allow list or deny list is limited only by the size of the policy. The maximum size of the entire policy is 25 KB (25,000 characters), which includes the allow list or deny list and any other parameters configured for other features.
      - This list works independently from OneDrive for Business and SharePoint Online allow/block lists. If you want to restrict individual file sharing in SharePoint Online, you need to set up an allow or deny list for OneDrive for Business and SharePoint Online.
      - The list does not apply to external users who have already redeemed the invitation. The list will be enforced after it is set up. If a user invitation is pending, and you set a policy that blocks their domain, the user’s attempt to redeem the invitation will fail.

        ![](../media/new1-5-11.png)

1. When finished, **Save** your changes.

## Summary

In this lab, you have successfully configured access reviews to manage user permissions for Teams and Groups, and set up external collaboration settings to control guest user access and invitations in Microsoft Entra ID. These configurations help enhance security and ensure proper access management within your organisation.

### You have successfully completed the lab.

By completing this **Hybrid Identity with Entra ID** hands-on lab, you have gained practical experience in designing and implementing a **Hybrid Identity solution using Microsoft Entra ID and Active Directory Domain Services**. You successfully configured identity synchronisation between on-premises and cloud environments using **Microsoft Entra Connect**, enabled **self-service password reset with password writeback**, and implemented **Privileged Identity Management (PIM)** for controlled and time-bound administrative access.

You also explored **identity governance and security monitoring** by configuring **access reviews, external collaboration settings, and Azure Monitor with Log Analytics** to track audit and sign-in activities. These configurations help ensure secure access management, visibility into identity-related events, and compliance with organisational security policies.

Overall, this lab provided a comprehensive understanding of how organisations can securely manage identities across **hybrid environments**, enforce **least-privilege access**, and implement **modern identity governance and monitoring capabilities** using Microsoft Entra ID.

