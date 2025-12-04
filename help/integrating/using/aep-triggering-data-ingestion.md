---
title: 通过 API 触发数据摄取
description: 了解如何通过API触发数据摄取。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Experienced
exl-id: d67a796a-0730-4502-802c-d0b3583dd1dc
hide: true
hidefromtoc: true
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 6%

---

# 通过 API 触发数据摄取 {#triggering-data-ingestion-apis}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector目前处于测试阶段，可能会频繁更新，恕不另行通知。 客户需要在Azure上托管（目前为仅北美测试版）才能访问这些功能。 如果您希望访问，请联系Adobe客户关怀。

Adobe Campaign Standard允许您通过API触发数据映射的直接摄取，并检索摄取请求的状态。

本页介绍如何触发和检索数据映射的摄取状态。 有关Campaign Standard API的全局信息，请参阅[此部分](../../api/using/get-started-apis.md)。

## 先决条件 {#prerequisites}

在使用API之前，必须先在Campaign Standard界面中配置并发布数据映射。 有关更多信息，请参阅一下章节。

* [映射定义](../../integrating/using/aep-mapping-definition.md)
* [映射激活](../../integrating/using/aep-mapping-activation.md)

创建数据映射后，必须将其停止运行，以便您可以随时从API触发它。 为此，请执行以下步骤：

1. 在Campaign Standard中，转到&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]**&#x200B;菜单。

1. 双击数据映射以将其打开，然后单击&#x200B;**[!UICONTROL Stop]**&#x200B;按钮。

   ![](assets/aep_datamapping_stop.png)

1. 保存更改

数据映射执行现已停止。 您可以使用Campaign Standard API手动触发它。

## 开始立即摄取数据映射 {#starting-immediate-ingestion}

通过POST操作，可触发将XDM映射立即摄取到Adobe Experience Platform：

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest`

>[!NOTE]
>
>为了执行摄取POST API调用，用户必须具有&#x200B;**SQL函数执行**&#x200B;角色，该角色可以由Campaign Standard管理员通过执行以下JS脚本来提供：
>
>```
>var sqlRoleObj = REST.head.roleBase.sql.get();
>REST.head.securityGroup.Administrators.roles.post(sqlRoleObj);
>```
>

POST操作返回有关已创建请求状态的信息：

* 已成功提交用于XDM映射的请求：

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

可以使用GET操作以及参数中的所需请求ID来检索摄取请求的状态：

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest
{"requestId"="<value>"}
```

>[!NOTE]
>
>有关XDM映射请求状态及其相关作业的详细信息，可在Campaign Standard界面的&#x200B;**[!UICONTROL Status of data export to platform]**&#x200B;菜单中获取（请参阅[映射激活](../../integrating/using/aep-mapping-activation.md)）。

GET操作将返回以下信息：

* **batchId**：只有在批次准备和上传后失败时，才会填充此字段，
* **信息**： XDM映射ID，
* **numRecords**：已摄取的记录数（仅限成功状态），
* **状态**：摄取请求状态（成功/失败/进行中）

对GET操作的可能响应包括：

* 摄取请求成功：

  ```
  {
  "batchId": "",
  "info": "Mapping Id: <value>. ",
  "numRecords": 15,
  "requestId": 3520,
  "status": "Success"
  }
  ```

* 摄取请求失败，已摄取0条记录：

  ```
  {
  "batchId": "",
  "info": "Mapping Id: <value>. ACP-880056 Failed to fetch the record from the database.",
  "numRecords": 0,
  "requestId": 3520,
  "status": "Failed"
  }
  ```

* 摄取请求失败，一些记录已上传到批次下：

  ```
  {
  "batchId": "<value>",
  "info": "Mapping Id: <value>. ACP-880096 Sync Job failed to upload. Please check the error in the Platform UI.",
  "numRecords": 0,
  "requestId": <value>,
  "status": "Failed"
  }
  ```

* 摄取某些记录后摄取请求中止（崩溃情况下可能会发生这种情况）：

  ```
  {
  "batchId": "",
  "info": "Mapping Id: <value>. Ingestion request aborted due to some issue with data ingestion service. Please submit a new request",
  "numRecords": 0,
  "requestId": <value>,
  "status": "Aborted"
  }
  ```

* 正在进行摄取请求（当请求以批次上传数据或批次正在为请求准备时）：

  ```
  {
  "batchId": "",
  "info": "Mapping Id: <value>.",
  "numRecords": 0,
  "requestId": <value>,
  "status": "In Progress"
  }
  ```
