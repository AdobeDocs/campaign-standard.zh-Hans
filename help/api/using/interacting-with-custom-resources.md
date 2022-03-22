---
title: 与自定义资源交互
description: 进一步了解使用API管理自定义资源/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 19bfeecb-da60-479c-a929-0cfb72ef59e3
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 4%

---

# 与自定义资源交互 {#interacting-with-custom-resources}

的 **/customResources** 端点允许您在REST中显示Campaign自定义资源。 基于此API，提供了自定义实体与外部端点之间的集成。

/customResources端点的行为与/profileAndServices端点完全相同。

此API中公开的自定义资源包括：

* /profileAndServicesExt下未显示的所有实体
* 所有与个人资料无关的实体，以及这些实体的子女和孙辈。
* 默认情况下，所有与任何事物都没有关联的实体及其子孙。

>[!NOTE]
>/profileAndServicesExt下可用的自定义资源在/customResources API中不会公开。


以下是从自定义资源检索元数据的示例：

```
GET /customResources/resourceType/<customResourceName>
```

要执行创建、更新或删除操作，请使用GET、POST、PATCH、DELETE。

```
POST /customResources/<customResourceName>
```

>[!NOTE]
>隐私API端点和工作流(/privacy/privacyTool)不会管理未链接到用户档案实体的自定义资源。
>您将负责管理和清理这些自定义资源的任何PII。 有关隐私工具的更多信息，请参阅 [单击此处](../../api/using/creating-a-privacy-request.md).
