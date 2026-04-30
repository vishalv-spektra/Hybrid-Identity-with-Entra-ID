# Lab 03: Implement and use Privileged Identity Management

#### Estimated Duration: 30 Minutes

## Overview

This lab focuses on setting up the use of Microsoft Entra to assign Global Administrator roles to specified users with defined privileges and durations. Then, manage and update existing role assignments, transitioning them from eligible to active status as needed, with specified durations and justifications.

## Objectives

In this lab, you will perform the following:
- Task 1: Assign Azure resource roles
- Task 2: Update or remove an existing Entra role assignment

### Task 1 - Assign Azure resource roles

In this task, you will assign the Global Administrator role to the users from Microsft Entra portal. 

1. Open a browser tab and sign in to Microsoft Entra Admin Center using your lab credentials. 

    ```
    https://entra.microsoft.com
    ```

   - Username : **<inject key="AzureAdUserEmail"></inject>**
   - Password : **<inject key="AzureAdUserPassword"></inject>**

2. Search **(1)** for and then select **Microsoft Entra Privileged Identity Management (2)**.

    ![](../media/L3T1S2.1-0903-1.png)

3. In the Privileged Identity Management page, in the left navigation, select **Microsoft Entra roles.**

    ![](../media/lab3-1.png)

4. In the left navigation menu, under **Manage**, select **Roles** to see the list of Entra roles.

    ![](../media/lab3-2.png)

5. On the top menu, select + **Add assignments**.

    ![](../media/lab3-3.png)

6. In the **Add assignments** page, select the **Select role** menu and then select **Global Administrator (1)**.

7. Under **Select member(s),** select **No member selected**.

8. In the Select members pane, select the following users **(3)** and then choose **Select (4)**.

    | Name           | 
      | -------------- | 
      | Edmund Reeve   | 
      | Miranda Snider | 
      | Allan Deyoung  | 
      | Joni Sherman   | 

    ![](../media/L3T1S8-0903.png)    

9. Select **Next (5)**.

10. On the **Settings** tab, under **Assignment type**, select **Eligible (1)**.

   - **Eligible** assignments require the member of the role to act to use the role. Actions might include performing a multi-factor authentication (MFA) check, providing a business justification, or requesting approval from designated approvers.

   - **Active** assignments do not require the member to perform any action to use the role. Members assigned as active have the privileges always assigned to the role.

11. **Uncheck (2)** the permanently eligible. Specify an assignment duration by changing the **start and end dates and times (3)**. 

12. When finished, select **Assign (4)**.

    ![](../media/L3T1S12-0903.png)

13. After the new role assignment is created, a status notification is displayed.

### Task 2 - Update or remove an existing Entra role assignment

In this task, you will update and remove an existing Entra role assignment as needed. 

1. Open **Microsoft Entra Privileged Identity Management** > **Microsoft Entra roles**.

1. Under **Manage**, select **Assignments (1)**.

1. On the **Eligible assignments (2)** tab, in the Action column, review the available options.

1. Select **Remove (3)** to remove any user from eligible assignments.

    ![](../media/L3T2S4-0903.png)

1. In the **Remove** dialog box, review the information and then select **Yes**.

    ![](../media/lab3-6.png)

1. To make the eligible assignment to active for any user, select **Update** from the Action list.

1. Provide the below details in **Membership settings** and click on **Save (5)**

     - Assignment type : **Active (1)**
     - Permanently eligible: **Uncheck the box (2)**
     - Assignment ends: Enter the next date **(3)**
     - Enter Justification : **Test (4)**
  
       ![](../media/L3T2S7.1-0903.png)

## Summary

In this lab, you have successfully assigned Azure resource roles with Privileged Identity Management using time-bound, eligible assignments with approval workflows. You have also updated and removed an existing Entra role assignment as needed.

#### You have successfully completed the lab. Click on Next >> to proceed with the next lab.

   ![](../media/up4.png)
