---
solution: Campaign Standard
product: campaign
title: 自定义资源
description: 进一步了解使用API进行自定义资源管理/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 3%

---


# 与自定义资源交互 {#interacting-with-custom-resources}

通过 **/customResources** endpoint，您可以在REST中显示ACS自定义资源。 基于此API，可在自定义实体和外部端点之间集成。

/customResources端点的行为与/profileAndServices端点的行为完全相同。

此API中公开的自定义资源包括：

* 链接到用户档案实体的所有实体
* 链接到用户档案实体子项的所有实体
* 所有与用户档案没有关联的实体，对于这些实体来说，还包括其子孙。

>[!NOTE]
>/profileAndServicesExt下提供的自定义资源不会在/customResources API中公开。

以下是一个从自定义资源检索元数据的示例：

```
GET /customResources/resourceType/<customResourceName>
```

要执行创建、更新或删除操作，请使用GET、POST、PATCH、DELETE。

```
POST /customResources/<customResourceName>
```

>[!NOTE]
>隐私API端点和工作流(/privacy/privacyTool)不管理未链接到用户档案实体的自定义资源。
>您有责任管理和清理这些自定义资源的任何PII。 有关隐私工具的更多信息，请 [单击此处](../../api/using/creating-a-privacy-request.md)。

