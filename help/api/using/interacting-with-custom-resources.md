---
title: 与自定义资源交互
description: 详细了解使用API进行自定义资源管理/
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

此 **/customResources** 端点允许您在REST中公开Campaign自定义资源。 基于此API，自定义实体和外部端点之间的集成可用。

/customResources端点的行为与/profileAndServices端点完全相同。

此API中公开的自定义资源包括：

* 所有未在/profileAndServicesExt下公开的实体
* 所有未与个人资料关联的实体，以及对于这些实体，为其子代和孙代。
* 默认情况下，所有未链接到任何内容的实体及其子项和孙项。

>[!NOTE]
>/profileAndServicesExt下可用的自定义资源不会在/customResources API中公开。


以下是从自定义资源检索元数据的示例：

```
GET /customResources/resourceType/<customResourceName>
```

要执行创建、更新或删除，请使用GET、POST、PATCH、DELETE。

```
POST /customResources/<customResourceName>
```

>[!NOTE]
>隐私API端点和工作流(/privacy/privacyTool)未管理未链接到用户档案实体的自定义资源。
>您将负责管理和清理这些自定义资源的任何PII。 有关隐私工具的更多信息， [单击此处](../../api/using/creating-a-privacy-request.md).
