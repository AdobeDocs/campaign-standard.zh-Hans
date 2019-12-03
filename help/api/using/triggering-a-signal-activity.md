---
title: 触发信号活动
description: 了解如何使用API触发信号活动。
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aee0e0437cbfe578cb2f715a2433099c79dd1748

---


# 触发信号活动 {#triggering-a-signal-activity}

在Adobe Campaign standard工作流程中，可能有一个或多个外部信 **号活动** 。 这些活动是等待触发的“监听器”。

Campaign Standard API允许您触发外部信 **号活动** ，以调用工作流。 API调用可以包括将被引入工作流的事件变量（要定位的受众名称、要导入的文件名、消息内容的一部分等）中的参数。 这样，您便可以轻松地将Campaign自动化与外部系统集成。

>[!NOTE]
>
>外部信号活动的触发频率不能超过每10分钟，并且目标工作流必须已经运行。

要触发工作流，请执行以下步骤：

1. 对工作流 **执行GET** 请求以检索外部信号活动触发器URL。

   `GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>`

1. 对返回 **的URL执行POST** 请求以触发信号活动，有效负荷中有 **“source”** 参数。 此属性是必填的，它允许您指示触发请求源。

如果要使用参数调用工作流，请使用“parameters”属性将其添 **加到有效负荷** 。 语法由参数的名称后跟其值组成(支持以下类型：字 **符串**&#x200B;数 **、数字**、 **boolean** 、 **date**/time)。

```
  -X POST <TRIGGER_URL>
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -H 'Content-Type: application/json;charset=utf-8' \
  -H 'Content-Length:79' \
  -i
  -d {
  -d    "source":"<SOURCE>",
  -d    "parameters":{
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>",
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>",
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>",  
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>"
  -d    }
  -d }
```

>[!NOTE]
>
>向有效负荷添加参数时，请确保其名 **称****** 和类型值与“外部信号”活动中声明的信息一致。 此外，有效载荷大小不应超过64Ko。

<br/>

***示例请求***

对工作流执行GET请求。

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

它返回工作流信号活动和关联的触发器url。

```
{
"PKey": "<PKEY>",
"activities": {
  "activity": {
    "signal1": {
      ...
      "trigger": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<PKEY>/activities/activity/<PKEY>/trigger/"
        },
        ...
      }
    }
  }
}
```

要触发信号活动，请在触发器url上使用“source”执行POST请求。 如果要使用参数调用工作流，请添加“参数”属性。

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<PKEY>/activities/activity/<PKEY>/trigger \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{
-d "source":"API",
-d "parameters":{
-d    "audience":"audience",
-d    "email":"anna.varney@mail.com",
-d    "template":"05",
-d    "contentURL":"http://www.adobe.com",
-d    "test":"true",
-d    "segmentCode":"my segment",
-d    "attribute":"2019-04-03 08:17:19.100Z"}
-d  }'
```

<!-- + réponse -->

如果外部信号活动中未声明其中一个参数，则POST请求将返回以下错误，指明缺少哪个参数。

```
RST-360011 An error has occurred - please contact your administrator.
'contentURL' parameter isn't defined in signal activity.
XTK-170006 Unable to parse expression 'HandleTrigger(@name, $(source), $({parameters}))'.
RST-360000 Error while assessing 'HandleTrigger(@name, $(source), $({parameters}))' expression ('xtk:workflow:execution/activities/signal/trigger' resource)
```
