---
solution: Campaign Standard
product: campaign
title: 控制工作流
description: 了解如何使用API控制工作流。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: 数据工程师
level: 富有经验
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 10%

---


# 控制工作流 {#controlling-a-workflow}

您可以通过包含工作流ID和所需执行命令的POST请求，直接从REST API控制工作流：

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands`

>[!CAUTION]
>
>如果在Adobe Campaign中更改了工作流ID，则API请求将不再工作。

有四个执行命令可用于控制工作流：

* 开始
* 暂停
* 继续
* 停止

有关执行命令的详细信息，请参阅[活动文档](https://docs.adobe.com/content/help/en/campaign-standard/using/managing-processes-and-data/executing-a-workflow/about-workflow-execution.html)。

<br/>

***示例请求***

* 开始工作流。

   ```
   -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -i
   -d '{"method":"start"}'
   ```

   <!-- + réponse -->

* 停止工作流。

   ```
   -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -i
   -d '{"method":"stop"}'
   ```

   <!-- + réponse -->
