---
title: "Call sharing and group call pickup"
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection: 
  - M365-voice
audience: Admin
appliesto: 
  - Microsoft Teams
ms.localizationpriority: medium
f1.keywords: 
 - CSH
ms.custom: 
 - ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
 - ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
 - Phone System
 - seo-marvel-mar2020
description: "Call sharing and group call pickup let users share incoming calls with colleagues so that calls can be captured when the user is unavailable."
---

# Call sharing and group call pickup in Microsoft Teams

The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.

Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.

To share calls with others, a user creates a call group and adds the users they want to share their calls with. Then they choose a simultaneous ring or forward setting. See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details. Note that mobile devices will only get notified if they're set for banner and ringtone.

> [!IMPORTANT]
> Users, the call group owner, and members of the call group must be in Teams Only deployment mode. For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).

## License required

Users must be assigned a Microsoft Teams Phone System license to set up and use call sharing and group call pickup. For additional details on the licensing model, see [Here's what you get with Phone System](/MicrosoftTeams/here-s-what-you-get-with-phone-system).

## Configure group call pickup

To set up group call pickup, a user first configures a call group (this is not the same as a security group or a Microsoft 365 group), and then adds the users they want to share their calls with. Then, they choose a simultaneous ring or call forward setting. For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).

Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users. Call groups cannot be created from security groups or Microsoft 365 groups; they must be created in Teams.

Admins should enable call groups via the **TeamsCallingPolicy AllowCallGroups** setting for a user. Admins can also enable this via Teams Admin portal.  In addition, the configured user can also configure their call groups via the client directly. Admin or end users cannot block the configuration by each other, but Teams Admin portal and Teams client should show this relationship accurately in both places. 

Important: When admins turn off call groups for users (after it has been turned on and the call group relationships are configured), the admins have to clean up the call group relationships for users in the Teams admin center to avoid incorrect call routing. 

## Limitations

Each configured call group can have a maximum of 25 users or 32,768 characters. 

## More information

[Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
