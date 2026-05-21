---
title: 数据模型概念
description: 了解 Adobe Campaign 数据模型及其修改方式。
audience: developing
content-type: reference
topic-tags: about-custom-resources
context-tags: cusResource,overview;eventCusResource,overview
feature: Data Model
role: Developer
level: Experienced
exl-id: 6e9e016a-473b-4a51-8bd6-c23c7b3d3610
TQID: https://experienceleague.adobe.com/jOKJ64oRWaLCf7C9V8ZTbrtSphd4cJrGLlyw0K4sFB8
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 251
ht-degree: 79%

---

# 数据模型概念{#data-model-concepts}

Adobe Campaign 提供了预定义的数据模型。 有权向现有资源添加新资源或扩展的[管理员](../../administration/using/users-management.md#functional-administrators)，可修改此数据模型。

>[!CAUTION]
>
>创建和修改资源是敏感操作，只能由专家用户执行。

通过 Adobe Campaign 徽标访问 **[!UICONTROL Administration]** > **[!UICONTROL Development]** 菜单，可管理&#x200B;**自定义资源**、**发布**&#x200B;这些资源，以及&#x200B;**访问诊断工具**。

Adobe Campaign 使用的数据，通过不同的资源进行定义。 您可通过创建自定义资源（如采购表或产品表）以&#x200B;**扩充提供的数据模板**。

无法修改内置资源（如营销策划、电子邮件或受众）。 但是，可以扩展自定义资源以添加新字段。

生成的扩展字段带有前缀，这样它们就不会与内置字段发生冲突。

>[!NOTE]
>
>您可以在[此页面](../../developing/using/datamodel-introduction.md)中找到内置资源的数据模型表示形式。

您还可在对应于所创建资源的屏幕中[配置导航](configuring-the-screen-definition.md)。

可以&#x200B;**导出和导入**&#x200B;自定义资源，例如从开发到生产环境。 有关更多信息，请参阅此[分步使用案例](../../automating/using/exporting-importing-custom-resources.md)。

>[!CAUTION]
>
>只有具有&#x200B;**[!UICONTROL Administration]**&#x200B;角色并有权访问&#x200B;**所有**&#x200B;单位的功能[管理员](../../administration/using/users-management.md#functional-administrators)才能访问发送日志、消息日志、跟踪日志、排除或订阅日志。 非管理员用户可以定位这些日志，但从链接表（用户档案、投放）开始。
