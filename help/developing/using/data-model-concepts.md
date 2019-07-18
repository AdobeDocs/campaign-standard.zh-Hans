---
title: 数据模型概念
seo-title: 数据模型概念
description: 数据模型概念
seo-description: 了解Adobe Campaign数据模型及其修改方法。
page-status-flag: 从未激活
uuid: cacd563f-6936-4b3e-83e3-5d4ae31d44e8
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: 关于自定义资源
discoiquuid: e0468da-3052-4ce5-8174-45aa1f5c4eed
context-tags: CusResource，概述；EventCusResource，概述
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: c880b265cf83cb76b2cdbe3cbdd77182adb71bb1

---


# Data model concepts{#data-model-concepts}

Adobe Campaign附带预定义的数据模型。[管理员](../../administration/using/types-of-users.md#functional-administrators) 可以修改现有资源中能够添加新资源或扩展的管理员。

>[!CAUTION]
>
>创建和修改资源是必须由专家用户执行的敏感操作。

**[!UICONTROL Administration]** 通过Adobe Campaign徽标访问的&gt; **[!UICONTROL Development]** 菜单允许您管理 **自定义资源**、 **发布** 和 **访问诊断工具**。

Adobe Campaign使用的数据是通过不同资源定义的。

You can **enrich the data template** that is provided by creating your own custom resources, such as purchase or product tables.

现成资源(如营销活动、电子邮件或受众)无法修改。但是，可以扩展自定义资源以添加新字段。

>[!NOTE]
>
>You can find a datamodel representation for the out-of-the-box resources [here](https://docs.campaign.adobe.com/doc/standard/en/datamodel/datamodel.html).

You can also **configure the navigation** in the screens corresponding to the resource created.

扩展字段是用前缀生成的，因此它们从不与现成字段冲突。
