---
solution: Campaign Standard
product: campaign
title: 触发信号活动
description: 了解如何使用API触发信号活动。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 2%

---


# 触发信号活动 {#triggering-a-signal-activity}

在Adobe Campaign Standard工作流程中，可以有一个或多个外 **部信号** 活动。 这些活动是等待被触发的“监听器”。

Campaign StandardAPI允许您触发 **外部信号** 活动来调用工作流。 API调用可以包括将被引入工作流的事件变量(受众名到目标、要导入的文件名、消息内容的一部分等)的参数。 这样，您便可以轻松地将活动自动化与外部系统集成。

>[!NOTE]
>
>外部信号活动不能比每10分钟触发一次的频率更高，并且目标工作流必须已运行。

要触发工作流，请按照以下步骤操作：

1. 在工作流 **上执** 行GET请求以检索外部信号活动触发器URL。

   `GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>`

1. 对返回 **的** URL执行POST请求 **，以触发信号活动，有效负荷中** 有“source”参数。 此属性是必需属性，它允许您指示触发请求源。

如果要使用参数调用工作流，请使用“parameters”属性将其 **添加到有效负荷** 中。 语法由参数的名称后跟其值组成(支持以下类型： **string****、** number **、** boolean ****&#x200B;和date/time)。

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
>向负载添加参数时，请确保其名 **称****和类型值** 与外部信号活动中声明的信息一致。 此外，有效载荷大小不应超过64Ko。

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

要触发信号活动，请在触发器url上使用“源”执行POST请求。 如果要使用参数调用工作流，请添加“参数”属性。

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

如果某个参数未在外部信号活动中声明，POST请求将返回以下错误，指明缺少哪个参数。

```
RST-360011 An error has occurred - please contact your administrator.
'contentURL' parameter isn't defined in signal activity.
XTK-170006 Unable to parse expression 'HandleTrigger(@name, $(source), $({parameters}))'.
RST-360000 Error while assessing 'HandleTrigger(@name, $(source), $({parameters}))' expression ('xtk:workflow:execution/activities/signal/trigger' resource)
```
