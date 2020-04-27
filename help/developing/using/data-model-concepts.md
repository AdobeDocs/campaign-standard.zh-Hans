---
title: 数据模型概念
description: 了解Adobe Campaign数据模型以及如何修改它。
page-status-flag: never-activated
uuid: cacd563f-6936-4b3e-83e3-5d4ae31d44e8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: about-custom-resources
discoiquuid: 4e0468da-3052-4ce5-8174-45aba1f5c4ed
context-tags: cusResource,overview;eventCusResource,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8852adb5edeb42eba1acf2911c988071104f1401

---


# 数据模型概念{#data-model-concepts}

Adobe Campaign包含预定义的数据模型。 此数据模型可由能够向现 [有资源](../../administration/using/users-management.md#functional-administrators) （或扩展）添加新资源或扩展的管理员修改。

>[!CAUTION]
>
>创建和修改资源是敏感操作，只能由专家用户执行。

通过 **[!UICONTROL Administration]** Adobe Campaign徽标访问的>菜单允许您管理自定义资 **[!UICONTROL Development]** 源 **,**&#x200B;发布 **，以及访******&#x200B;问诊断工具。

Adobe Campaign使用的数据通过不同的资源来定义。 您可以 **通过创建自己的自定义资源** （如购买表或产品表）来丰富提供的数据模板。

无法修改内置资源(如活动、电子邮件或受众)。 但是，可以扩展自定义资源以添加新字段。

扩展字段会生成前缀，这样它们就不会与内置字段发生冲突。

>[!NOTE]
>
>您可以在此页中查找内置资源的数据模型 [表示形式](../../developing/using/datamodel-introduction.md)。

您还可以在 [与创建的资源对应的屏幕中](configuring-the-screen-definition.md) ，配置导航。

可以导出和 **导入自定义资源** ，例如从开发到生产环境。 有关此内容的详细信息，请 [参阅此分步使用案例](../../automating/using/exporting-importing-custom-resources.md)。
