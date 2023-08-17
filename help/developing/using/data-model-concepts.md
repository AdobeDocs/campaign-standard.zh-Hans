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
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 79%

---

# 数据模型概念{#data-model-concepts}

Adobe Campaign 提供了预定义的数据模型。有权向现有资源添加新资源或扩展的[管理员](../../administration/using/users-management.md#functional-administrators)，可修改此数据模型。

>[!CAUTION]
>
>创建和修改资源是敏感操作，只能由专家用户执行。

通过 Adobe Campaign 徽标访问 **[!UICONTROL Administration]** > **[!UICONTROL Development]** 菜单，可管理&#x200B;**自定义资源**、**发布**&#x200B;这些资源，以及&#x200B;**访问诊断工具**。

Adobe Campaign 使用的数据，通过不同的资源进行定义。您可通过创建自定义资源（如采购表或产品表）以&#x200B;**扩充提供的数据模板**。

无法修改内置资源（如营销策划、电子邮件或受众）。但是，可以扩展自定义资源以添加新字段。

生成的扩展字段带有前缀，这样它们就不会与内置字段发生冲突。

>[!NOTE]
>
>您可以在中找到内置资源的数据模型表示形式 [此页面](../../developing/using/datamodel-introduction.md).

您还可在对应于所创建资源的屏幕中[配置导航](configuring-the-screen-definition.md)。

可以&#x200B;**导出和导入**&#x200B;自定义资源，例如从开发到制作环境。有关更多信息，请参阅此[分步使用案例](../../automating/using/exporting-importing-custom-resources.md)。

>[!CAUTION]
>
>仅功能 [管理员](../../administration/using/users-management.md#functional-administrators)，替换为 **[!UICONTROL Administration]** 角色和访问权限 **全部** 单位可访问发送日志、消息日志、跟踪日志、排除或订阅日志。 非管理员用户可以定位这些日志，但从链接表（用户档案、投放）开始。
