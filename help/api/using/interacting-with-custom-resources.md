---
title: 与自定义资源交互
description: 了解有关使用API进行自定义资源管理的更多信息/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 19bfeecb-da60-479c-a929-0cfb72ef59e3
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 0%
---
# 与自定义资源交互 {#interacting-with-custom-resources}

**/customResources**&#x200B;端点允许您在REST中公开Campaign自定义资源。 基于此API，可在自定义实体和外部端点之间实现集成。

/customResources端点的行为与/profileAndServices端点完全相同。

此API中公开的自定义资源包括：

* 所有未在/profileAndServicesExt下公开的实体
* 所有与个人资料无关的实体，对于这些实体，还包括其子代和孙代。
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
>隐私API端点和工作流(/privacy/privacyTool)不管理未链接到用户档案实体的自定义资源。
>您将负责管理和清理这些自定义资源的任何PII。 有关隐私工具的更多信息，[单击此处](../../api/using/creating-a-privacy-request.md)。
