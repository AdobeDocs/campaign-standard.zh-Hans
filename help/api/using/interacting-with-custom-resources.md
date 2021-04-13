---
solution: Campaign Standard
product: campaign
title: 自定义资源
description: 了解有关使用API进行自定义资源管理的更多信息/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 19bfeecb-da60-479c-a929-0cfb72ef59e3
translation-type: tm+mt
source-git-commit: 01e4eb027b55815c3680b26691e61cbe5b63ee8c
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 3%

---

# 与自定义资源交互 {#interacting-with-custom-resources}

**/customResources**&#x200B;端点允许您在REST中公开活动自定义资源。 基于此API，可在自定义实体和外部端点之间集成。

/customResources端点的行为与/profileAndServices端点的行为完全相同。

此API中公开的自定义资源包括：

* 未在/profileAndServicesExt下公开的所有实体
* 所有与用户档案没有联系的实体，对于这些实体，还有其子孙。
* 默认情况下，所有与任何事物没有关联的实体及其子孙。

>[!NOTE]
>/profileAndServicesExt下提供的自定义资源不会在/customResources API中公开。


下面是一个从自定义资源检索元数据的示例：

```
GET /customResources/resourceType/<customResourceName>
```

要执行创建、更新或删除操作，请使用GET、POST、PATCH、DELETE。

```
POST /customResources/<customResourceName>
```

>[!NOTE]
>隐私API端点和工作流(/privacy/privacyTool)不管理未链接到用户档案实体的自定义资源。
>您有责任管理和清理这些自定义资源的任何PII。 有关隐私工具的详细信息，请[单击此处](../../api/using/creating-a-privacy-request.md)。
