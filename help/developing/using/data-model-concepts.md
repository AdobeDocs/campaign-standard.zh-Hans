---
title: 数据模型概念
description: 了解Adobe Campaign数据模型以及如何修改它。
page-status-flag: 从未激活
uuid: cacd563f-6936-4b3e-83e3-5d4ae31d44e8
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 开发
content-type: 参考
topic-tags: about-custom-resources
discoiquuid: 4e0468da-3052-4ce5-8174-45aba1f5c4ed
context-tags: cusResource,overview;eventCusResource,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 数据模型概念{#data-model-concepts}

Adobe Campaign附带预定义的数据模型。 此数据模型可由能够向现 [有资源](../../administration/using/users-management.md#functional-administrators) （或扩展）添加新资源或扩展的管理员修改。

>[!CAUTION]
>
>创建和修改资源是敏感操作，只能由专家用户执行。

通过 **[!UICONTROL Administration]** Adobe Campaign徽 **[!UICONTROL Development]** 标访问的 **&gt;菜单允许您管理自定义资源**, **发布** ，以及访 ****&#x200B;问诊断工具。

Adobe Campaign使用的数据是通过不同资源定义的。

您可以 **通过创建自己的自定义资源** （如购买表或产品表）来丰富提供的数据模板。

无法修改现成资源（如营销活动、电子邮件或受众）。 但是，可以扩展自定义资源以添加新字段。

>[!NOTE]
>
>您可以在此处找到现成的资源的数据模型表示 [形式](https://docs.campaign.adobe.com/doc/standard/en/datamodel/datamodel.html)。

您还可以在 **与创建的资源对应的屏幕中** ，配置导航。

扩展字段会生成前缀，这样它们就不会与现成的字段发生冲突。
