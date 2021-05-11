---
solution: Campaign Standard
product: campaign
title: 通过 API 触发数据摄取
description: 了解如何通过API触发数据摄取。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM集成
role: Data Architect
level: Experienced
exl-id: d67a796a-0730-4502-802c-d0b3583dd1dc
translation-type: tm+mt
source-git-commit: a4e1edc23cf750e44026f388f7b0fff3a80ec663
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 4%

---

# 通过 API 触发数据摄取 {#triggering-data-ingestion-apis}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector目前处于测试阶段，可能会在不通知的情况下频繁进行更新。 客户需要托管在Azure上（目前仅针对北美）才能访问这些功能。 如果您希望访问，请联系Adobe客户关怀团队。

Adobe Campaign Standard允许您通过API触发数据映射的即时摄取，并检索摄取请求的状态。

本页介绍如何触发和检索数据映射的摄取状态。 有关Campaign Standard API的全局信息，请参阅[本节](../../api/using/get-started-apis.md)。

## 先决条件{#prerequisites}

在使用API之前，必须首先在Campaign Standard界面中配置和发布数据映射。 有关详细信息，请参阅以下部分：

* [映射定义](../../integrating/using/aep-mapping-definition.md)
* [映射激活](../../integrating/using/aep-mapping-activation.md)

创建数据映射后，必须停止它的运行，以便您可以随时从API触发它。 为此，请执行以下步骤：

1. 在Campaign Standard中，转到&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]**&#x200B;菜单。

1. 多次单击数据映射以将其打开，然后单击&#x200B;**[!UICONTROL Stop]**&#x200B;按钮。

   ![](assets/aep_datamapping_stop.png)

1. 保存更改

数据映射执行现已停止。 您可以使用Campaign Standard API手动触发它。

## 开始立即获取数据映射{#starting-immediate-ingestion}

通过POST操作触发XDM映射到Adobe Experience Platform的即时引入：

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest`

>[!NOTE]
>
>要执行收录POST API调用，用户必须具有&#x200B;**SQL函数执行**&#x200B;角色，Campaign Standard管理员可通过执行以下JS脚本来提供该角色：
>
>
```
>var sqlRoleObj = REST.head.roleBase.sql.get();
>REST.head.securityGroup.Administrators.roles.post(sqlRoleObj);
>```

POST操作返回有关已创建请求状态的信息：

* 已成功提交XDM映射请求：

```
{
"requestId": <value>,
"info": "Ingestion request submitted successfully for the Mapping ID: <value>",
"status":"Success"
}
```

* XDM映射的请求已在进行中：

```
{
"requestId": <value>,
"info": "Ingestion request already in progress for the Mapping ID: <value>",
"status":"In Progress"
}
```

* 请求失败，因为XDM映射未发布或已停止：

```
{
"info": "Unable to submit data ingestion request, XDM Mapping ID: <value> is not stopped",
"status": "Failed"
}
{
"info": "Unable to submit data ingestion request, XDM Mapping ID: <value> is not published",
"status": "Failed"
}
```

## 检索摄取请求{#retrieving-status}的状态

可以使用GET操作和参数中所需的请求ID来检索摄取请求的状态：

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest
{"requestId"="<value>"}
```

>[!NOTE]
>
>有关XDM映射请求状态及其相关作业的详细信息，可在&#x200B;**[!UICONTROL Status of data export to platform]**&#x200B;菜单的Campaign Standard接口中找到(请参阅[映射激活](../../integrating/using/aep-mapping-activation.md))。

GET操作返回以下信息：

* **batchId**:仅当批准备和上传后出现故障时，才填充此字段，
* **信息**:XDM映射ID，
* **numRecords**:已摄取的记录数（仅限成功状态），
* **状态**:收录请求状态(success/failed/in progress)

对GET操作的可能响应有：

* 收录请求成功：

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. ",
   "numRecords": 15,
   "requestId": 3520,
   "status": "Success"
   }
   ```

* 收录请求失败，收录0个记录：

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. ACP-880056 Failed to fetch the record from the database.",
   "numRecords": 0,
   "requestId": 3520,
   "status": "Failed"
   }
   ```

* 收录请求失败，某些记录在批处理下上传：

   ```
   {
   "batchId": "<value>",
   "info": "Mapping Id: <value>. ACP-880096 Sync Job failed to upload. Please check the error in the Platform UI.",
   "numRecords": 0,
   "requestId": <value>,
   "status": "Failed"
   }
   ```

* 在收录某些记录后，收录请求已中止（在崩溃情况下可能发生这种情况）：

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. Ingestion request aborted due to some issue with data ingestion service. Please submit a new request",
   "numRecords": 0,
   "requestId": <value>,
   "status": "Aborted"
   }
   ```

* 正在收录请求（当请求在批中上载数据或正在为请求准备批时）：

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>.",
   "numRecords": 0,
   "requestId": <value>,
   "status": "In Progress"
   }
   ```
