---
title: 通过 API 触发数据摄取
description: 了解如何通过API触发数据摄取。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: d67a796a-0730-4502-802c-d0b3583dd1dc
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 6%

---

# 通过 API 触发数据摄取 {#triggering-data-ingestion-apis}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector目前处于测试阶段，可能会频繁更新，恕不另行通知。 需要在Azure上托管客户（目前仅适用于北美地区的测试版）才能访问这些功能。 如果您希望访问，请联系Adobe客户关怀团队。

Adobe Campaign Standard允许您通过API触发数据映射的立即摄取，并检索摄取请求的状态。

本页介绍如何触发和检索数据映射的摄取状态。 有关Campaign StandardAPI的全局信息，请参阅[此部分](../../api/using/get-started-apis.md)。

## 先决条件 {#prerequisites}

在使用API之前，必须先在Campaign Standard界面中配置并发布数据映射。 有关更多信息，请参阅一下章节。

* [映射定义](../../integrating/using/aep-mapping-definition.md)
* [映射激活](../../integrating/using/aep-mapping-activation.md)

创建数据映射后，必须停止该映射运行，以便您可以随时从API触发该映射。 为此，请执行以下步骤：

1. 在Campaign Standard中，转到&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]**&#x200B;菜单。

1. 双击数据映射以将其打开，然后单击&#x200B;**[!UICONTROL Stop]**&#x200B;按钮。

   ![](assets/aep_datamapping_stop.png)

1. 保存更改

数据映射执行现已停止。 您可以使用Campaign StandardAPI手动触发。

## 开始立即摄取数据映射 {#starting-immediate-ingestion}

通过POST操作，可触发将XDM映射立即摄取到Adobe Experience Platform:

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest`

>[!NOTE]
>
>要执行摄取POSTAPI调用，用户必须具有&#x200B;**SQL函数执行**&#x200B;角色，Campaign Standard管理员可通过执行以下JS脚本来提供该角色：
>
>
```
>var sqlRoleObj = REST.head.roleBase.sql.get();
>REST.head.securityGroup.Administrators.roles.post(sqlRoleObj);
>```

POST操作会返回与创建的请求状态有关的信息：

* 已成功为XDM映射提交请求：

```
{
"requestId": <value>,
"info": "Ingestion request submitted successfully for the Mapping ID: <value>",
"status":"Success"
}
```

* 正在为XDM映射请求：

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

## 检索摄取请求的状态 {#retrieving-status}

可以通过GET操作和参数中的所需请求ID来检索摄取请求的状态：

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest
{"requestId"="<value>"}
```

>[!NOTE]
>
>有关XDM映射请求状态及其相关作业的详细信息，请参阅&#x200B;**[!UICONTROL Status of data export to platform]**&#x200B;菜单的Campaign Standard界面（请参阅[映射激活](../../integrating/using/aep-mapping-activation.md)）。

GET操作会返回以下信息：

* **batchId**:仅当批量准备和上传失败时，才会填充此字段，
* **信息**:XDM映射ID，
* **numRecords**:已摄取的记录数（仅限成功状态）、
* **状态**:摄取请求状态（成功/失败/正在进行）

对GET操作的可能响应包括：

* 成功摄取请求：

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. ",
   "numRecords": 15,
   "requestId": 3520,
   "status": "Success"
   }
   ```

* 摄取请求失败，摄取了0个记录：

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. ACP-880056 Failed to fetch the record from the database.",
   "numRecords": 0,
   "requestId": 3520,
   "status": "Failed"
   }
   ```

* 摄取请求失败，某些记录在批次下上传：

   ```
   {
   "batchId": "<value>",
   "info": "Mapping Id: <value>. ACP-880096 Sync Job failed to upload. Please check the error in the Platform UI.",
   "numRecords": 0,
   "requestId": <value>,
   "status": "Failed"
   }
   ```

* 摄取某些记录后，摄取请求中止（在崩溃情况下可能会发生这种情况）：

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. Ingestion request aborted due to some issue with data ingestion service. Please submit a new request",
   "numRecords": 0,
   "requestId": <value>,
   "status": "Aborted"
   }
   ```

* 正在摄取请求（当请求以批量方式上传数据或正在为请求准备批处理时）：

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>.",
   "numRecords": 0,
   "requestId": <value>,
   "status": "In Progress"
   }
   ```
