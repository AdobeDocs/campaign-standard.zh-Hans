---
title: 通过API触发数据摄取
description: 了解如何通过API触发数据摄取。
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 67223cf8eed46e2431c03674bd837262e37c7473

---


# 通过API触发数据摄取 {#triggering-data-ingestion-apis}

>[!IMPORTANT]
>
>Campaign Standard Data服务目前处于测试阶段，可能会在不另行通知的情况下频繁进行更新。 客户必须托管在Azure上（目前仅针对北美）才能访问这些功能。 如果您希望访问，请联系Adobe客户关怀。

Adobe Campaign standard允许您通过API触发数据映射的即时摄取，并检索摄取请求的状态。

本页介绍如何触发和检索数据映射的摄取状态。 有关Campaign Standard API的全局信息，请参 [阅本节](../../api/using/about-campaign-standard-apis.md)。

## 先决条件 {#prerequisites}

在使用API之前，数据映射必须首先在Campaign standard界面中配置并发布。 有关详细信息，请参阅以下各节：

* [映射定义](../../administration/using/aep-mapping-definition.md)
* [映射激活](../../administration/using/aep-mapping-activation.md)

创建数据映射后，必须停止它的运行，以便您可以随时从API触发它。 为此，请执行以下步骤：

1. 在Campaign Standard中，转到 **[!UICONTROL Administration]**>**[!UICONTROL Development]** > **[!UICONTROL Platform]**>菜**[!UICONTROL Status of data export to platform]** 单。

1. 双击数据映射以将其打开，然后单击按 **[!UICONTROL Stop]**钮。

   ![](assets/aep_datamapping_stop.png)

1. 保存更改

数据映射执行现已停止。 您可以使用Campaign Standard API手动触发它。

## 开始立即获取数据映射 {#starting-immediate-ingestion}

通过POST操作可立即将XDM映射引入Adobe Experience Platform:

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest`

>[!NOTE]
>
>要执行收录POST API调用，用户必须具有 **SQL函数执行角色** ,Campaign standard管理员可通过执行以下JS脚本提供该角色：
>
>`var sqlRoleObj = REST.head.roleBase.sql.get();
REST.head.securityGroup.Administrators.roles.post(sqlRoleObj);`

POST操作会返回有关已创建请求状态的信息：

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

## 检索摄取请求的状态 {#retrieving-status}

可以使用GET操作和参数中的所需请求ID来检索摄取请求的状态：

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest
{"requestId"="<value>"}
```

>[!NOTE]
有关XDM映射请求状态及其相关作业的详细信息，请参阅Campaign standard界面中的“数据导出到平台的状态”菜单 **!UICONTROL [(请参阅]** 映射激活 [](../../administration/using/aep-mapping-activation.md))。

GET操作返回以下信息：

* **batchId**:仅当在批准备和上传后失败时，才填充此字段，
* **info**:XDM映射ID,
* **numRecords**:已摄取的记录数（仅限成功状态）,
* **status**:收录请求状态(success/failed/in progress)

对GET操作的可能响应包括：

* 收录请求成功：

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. ",
   "numRecords": 15,
   "requestId": 3520,
   "status": "Success"
   }
   ````

* 收录请求失败，收录了0个记录：

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. ACP-880056 Failed to fetch the record from the database.",
   "numRecords": 0,
   "requestId": 3520,
   "status": "Failed"
   }
   ```

* 收录请求失败，某些记录以批次上载：

   ````
   {
   "batchId": "<value>",
   "info": "Mapping Id: <value>. ACP-880096 Sync Job failed to upload. Please check the error in the Platform UI.",
   "numRecords": 0,
   "requestId": <value>,
   "status": "Failed"
   }
   ```
   
* 在摄取某些记录后，收录请求中止（在崩溃情况下可能发生这种情况）:

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. Ingestion request aborted due to some issue with data ingestion service. Please submit a new request",
   "numRecords": 0,
   "requestId": <value>,
   "status": "Aborted"
   }
   ```

* 正在收录请求（当请求以批次上传数据或准备批次请求时）:

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>.",
   "numRecords": 0,
   "requestId": <value>,
   "status": "In Progress"
   }
   ```
