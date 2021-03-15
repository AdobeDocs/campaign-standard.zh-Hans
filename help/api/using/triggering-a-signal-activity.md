---
solution: Campaign Standard
product: campaign
title: 触发信号活动
description: 了解如何使用API触发信号活动。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: 数据工程师
level: 富有经验
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 2%

---


# 触发信号活动 {#triggering-a-signal-activity}

在Adobe Campaign Standard工作流中，可以有一个或多个&#x200B;**外部信号**&#x200B;活动。 这些活动是等待被触发的“监听器”。

Campaign Standard API允许您触发&#x200B;**外部信号**&#x200B;活动以调用工作流。 API调用可以包括将被引入工作流的事件变量(要导入的受众名、要导入的文件名、消息内容的一部分等)中的参数。 这样，您就可以轻松地将活动自动化与外部系统集成。

>[!NOTE]
>
>外部信号活动的触发频率不能超过每10分钟，并且目标工作流必须已在运行。

要触发工作流，请执行以下步骤：

1. 在工作流上执行&#x200B;**GET**&#x200B;请求以检索外部信号活动触发器URL。

   `GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>`

1. 对返回的URL执行&#x200B;**POST**&#x200B;请求以触发信号活动，负载中有&#x200B;**&quot;source&quot;**&#x200B;参数。 此属性是必填项，它允许您指示触发请求源。

如果要使用参数调用工作流，请使用&#x200B;**&quot;parameters&quot;**&#x200B;属性将其添加到有效负荷中。 语法由参数的名称后跟其值组成(支持以下类型：**string**、**number**、**boolean**&#x200B;和&#x200B;**date/time**)。

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
>向负载添加参数时，请确保其&#x200B;**name**&#x200B;和&#x200B;**type**&#x200B;值与“外部信号”活动中声明的信息一致。 此外，有效载荷大小不应超过64Ko。

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

如果某个参数未在外部信号活动中声明，则POST请求将返回以下错误，指示缺少哪个参数。

```
RST-360011 An error has occurred - please contact your administrator.
'contentURL' parameter isn't defined in signal activity.
XTK-170006 Unable to parse expression 'HandleTrigger(@name, $(source), $({parameters}))'.
RST-360000 Error while assessing 'HandleTrigger(@name, $(source), $({parameters}))' expression ('xtk:workflow:execution/activities/signal/trigger' resource)
```
