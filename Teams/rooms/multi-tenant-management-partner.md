﻿---
title: Multi-tenant customer management for partners
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: dstrome 
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection: 
  - M365-collaboration
  - m365initiative-meetings
appliesto: 
  - Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Mult-tenant customer management for partners.
f1keywords: 
---


# Multi-tenant customer management for partners

Multi-tenant management (MTM) in the Teams Rooms Managed (TRM) service helps partner organizations manage multiple customers in one place, with their own domain credentials. Partner users will only see customer rooms that they are assigned to manage. It is possible to apply custom roles for each customer in the MTM tenant, giving partner organizations granular control of permissions to the customer’s resources. 

The MTM portal can be accessed through this [link](https://partner.rooms.microsoft.com/).

> [!Note] 
> Partner organizations cannot manage their own rooms through the MTM portal. Those rooms can be managed in the [TRM portal](https://portal.rooms.microsoft.com/). 

## Pre-requisites for managing your customers through the MTM experience

To gain access to the MTM portal, your organization must be onboarded as an Elite Partner for the TRM service. To become an Elite partner contact askelite@microsoft.com.


## On-boarding customers

To manage customers through the TRM-MTM portal, a relationship must be established between the partner organization’s tenant and the customer through an invitation sent by the customer. 

### Invitation from the customer

The partner provides the user principle names (UPNs) of the users who will be primary administrators assigned to the customer. Only the users identified in the invitation can see and accept the invitation when they log in to the TRM-MTM portal. 

> [!Note]
> Even if you have elevated privileges such as Global Administrator, you will not see the invitation unless you are explicitly added. 

Details on the customer invitation are outlined in [Multi-tenant management for Customers](multi-tenant-management-customer.md).

**To accept a pending invite**

1. Log in to the TRM-MTM portal as one of the users on the invitation.
1. Go to **Customers**.
1. Select the invitation showing with a status of “Pending”.
1. Review the invitation details.
1. Select **Accept** to establish the partner-customer relationship.

   Selecting **Deny** deletes the invitation for the user denying. The invitation is still available for other users that have not yet acted.

   > [!Note]
   > The invitation is unique, and independent for each user. The first user to accept establishes the link between the partner and customer tenant. There is no permanent association with the user that establishes the link. Subsequent users who accept the invitation are added as Primary admins.

   > [!Note]
   > *If a partner user accidentally denies the invitation, it is best to have another user simply add them to the Partner role (or any other RBAC role) for that customer.* 

After accepting the invitation, the user is automatically added as a Primary admin for this customer's tenant. 

To review the configuration for this tenant, select the customer in the **Customers** list.


## Off-boarding customers

To off-board a customer, you must remove them from the Customers list.

**To remove a customer** 

1. Login to the TRM-MTM portal as a Primary admin for the customer you wish to remove.
1. Go to **Customers**.
1. Select the customer you wish to remove.
1. In the customer detail pane, select **Remove customer**.
1. Select **Delete** in the confirmation prompt to terminate the association between your and the customer tenant.


## Managing partner roles

Partner roles allow for delegation of responsibilities to additional personnel. The concept of these roles is the same as described in [Role-based access control](microsoft-teams-rooms-premium-rbac.md), but in context of each customer. Further, it is important to note that partner roles are distinct from the customer’s roles. The partner roles can be deleted by the customer. 

The **Primary admins** role is the only built-in role for each on-boarded customer and has almost all permissions —– in context of the customer —– for the TRM service (see table 1). Partner** role permissions only extend as far as the rooms designated by the customer. For example, if the cCustomer is a global organization and assigns the Partner to manage All US rooms, the primary admin would only be able to manage and delegate permissions for those rooms. The Partner has no visibility to other rooms the Customer may have in other countries. 

> [!Important]
> There must always be at least one user in the **Primary admins** role.

**To manage users in the **Partner** role for a customer**

1. Go to **Settings > Roles**. 
1. Select the customer from the drop-down list for which you want to edit the partner role.
1. Select the **Primary admins** built-in role from the list.
1. Select **Assignments.**
1. From the list, select **Invited Admins.**
1. Select **Members.**
1. Click Select **Edit.** 
1. Search for the user or security group you wish to add in the search bar.
1. Select the user or group .
1. Click Select **Save** to confirm the changes.

### Managing custom partner roles for a customer

As a partner, you can create custom roles to suit your operational requirements. For example, you might create a help desk role that should only have incident management permissions. 

**To manage roles**

1. Go to **Settings > Roles**. 
1. Select the customer from the drop down for which you want to edit the partner role.
1. Create a [custom role](microsoft-teams-rooms-premium-rbac.md#built-in-roles).




|Feature|Permission|**MMR Admin**|**Site Lead**|**Site Tech**|**Primary admins**|
| :- | :- | :- | :- | :- | :- |
|Rooms|View|||||
||Modify|||||
||Reset key|||||
||Download key|||||
||Unenroll|||||
|Group management|Create |||||
||View|||||
||Modify|||||
|Update ring management|Create |||||
||View|||||
||Modify|||||
|Reports|View|||||
|Ticket management|Create customer incident|||||
||View|||||
||Update|||||
|MMR Settings|View|||||
||Modify|||||
|Role management|View |||||
||Modify|||||

> [!Note]
> A user assigned as a Primary admin for Customer A has full permissions in the TRM service for only that customer. The permissions of the user in Customer A have no influence on other customers.

## Security

End customers retain control over access to their data and can completely remove a partner or specific roles at any time.

With the delegated access feature, a partner does not gain any other privileges outside of the TRM service portal. For example, by using this feature to invite a partner to manage rooms in the TRM service, no permissions are granted to AAD or the Teams Admin Center or any other Microsoft product. In addition, partners do not have any access to view  or modify rooms not defined in the invitation scope.

Once the partner-customer relationship is established – as described in the “Onboarding customers” of this doc – the partner can view room data in the TRM service. This includes any data present in the TRM service but derived from other Microsoft products. For example, call quality reports in the TRM portal are derived from Teams call quality data.

Data resides in the customer’s tenant and is not copied to the partner’s tenant. 

The MTM portal uses AAD authentication to validate the login credentials of the partner. It is important to note that at this time, the customer’s authentication policies will not apply to the partner. For example, if the customer has a multi-factor authentication policy, it does not translate to the partner.

The customer can pull audit logs for the TRM service, which includes partner activity. See [Audit logging in the Teams Rooms Managed service](multi-tenant-auditing.md).

> [!Note]
> AAD auditing and O365 auditing does not capture logs from the TRM portal.

## Navigating the MTM portal

The MTM portal has two interactive models to navigate between customer data:

- Aggregate views were data from all your customers is consolidated in a single list and can be filtered.

  > [!Note]
  > This view is only supported in the **Incidents** page when **Enable all tickets view** is toggled on.

  ![Figure 1](../media/multi-tenant-management-partner-001.png)

 - Tenant switching where only data from the **Customer** selected in the drop-down list is displayed.
