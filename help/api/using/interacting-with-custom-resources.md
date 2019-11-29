---
title: 自定义资源
description: 进一步了解使用API进行自定义资源管理/
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
source-git-commit: 5c4d3fc9853bf9bad4efcefaea242fecc9c4c61f

---


# 与自定义资源交互 {#interacting-with-custom-resources}

通过 **/customResources端点** ，您可以在REST中显示ACS自定义实体。 基于此API，可在自定义实体和外部端点之间集成。

/customResources与/profileAndServices端点具有完全相同的行为。

在此API中公开的自定义实体包括：

* 链接到配置文件实体的所有实体
* 链接到配置文件实体子项的所有实体
* 所有与个人资料没有关联的实体，以及这些实体的子孙。

>[!NOTE]
>/profileAndServicesExt下可用的自定义实体不在/customResources API中公开。

以下是一个从自定义资源检索元数据的示例：

```
GET /customResources/resourceType/<customResourceName>
```

要执行创建、更新或删除操作，请使用GET、POST、PATCH、DELETE。

```
POST /customResources/<customResourceName>
```

>[!NOTE]
>隐私API端点和工作流(/privacy/privacyTool)不管理未链接到配置文件实体的自定义资源。
>您有责任管理和清理这些自定义资源的任何PII。 有关隐私工具的详细信息，请单 [击此处](../../api/using/privacy-management.md)。