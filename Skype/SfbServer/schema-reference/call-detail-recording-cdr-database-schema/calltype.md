---
title: "CallType table in Skype for Business Server 2015"
ms.reviewer: 
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: "The CallType table is a static table that stores the list of possible call types."
---

# CallType table in Skype for Business Server 2015
 
The CallType table is a static table that stores the list of possible call types.
  
|**Column**|**Data Type**|**Key/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Primary  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || Allowed values: <br/>  0 -- Unknown <br/>  1 - Instant Messaging <br/>  2 -- Application Sharing <br/>  3 -- Audio <br/>  4 - Audio and Video <br/>  5 - File Transfer <br/> |
   

