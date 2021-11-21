---
title: 筛选规则
description: 使用过滤规则优化消息的受众。
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
feature: Typology Rules
role: User
level: Intermediate
exl-id: 43e97f3c-ed82-4fcc-ac0d-fcee6a22da35
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 3%

---

# 筛选规则 {#filtering-rules}

利用筛选规则，可根据查询中定义的条件排除部分消息目标，例如已隔离的用户档案或已发送了特定数量电子邮件的用户档案。

## 默认筛选分类规则 {#default-filtering-typology-rules}

下表提供了有关现成筛选规则及其相关渠道的信息。

| 标签 | 渠道 | 说明 |
| ---------|----------|---------|
| **[!UICONTROL Address not specified]** | 所有 | 排除没有指定地址（电子邮件、邮政地址等）的目标群体。 )。 |
| **[!UICONTROL Address on denylist]** | 所有 | 不包括中的地阻止列表址。 |
| **[!UICONTROL Duplicate]** | 所有 | 根据目标群体排除重复项 **[!UICONTROL Address]** 字段。 |
| **[!UICONTROL Exclude mobile applications]** | 移动应用程序 | 不包括与消息中定义的移动应用程序不匹配的应用程序订阅。 |
| **[!UICONTROL Exclude mobile applications for In-App]** | 应用程序内 | 不包括与消息中定义的移动应用程序不匹配的应用程序订阅（应用程序内模板）。 |
| **[!UICONTROL Exclude mobile applications for In-App broadcast]** | 应用程序内 | 不包括与消息中定义的移动应用程序不匹配的应用程序订阅（应用程序内广播模板） |
| **[!UICONTROL Exclude mobile applications for Push]** | 移动应用程序 | 不包括与消息中定义的移动应用程序不匹配的应用程序订阅（用于推送） |
| **[!UICONTROL Quarantined address]** | 所有 | 排除隔离的地址。 |
| **[!UICONTROL Target limited in size]** | 所有 | 检查是否达到目标的最大投放大小。 适用于激活“投放限制”选项的直邮投放。 |

除了这些默认筛选规则之外，还提供了两个排除规则：

* **[!UICONTROL Exclusion of addresses]** ( **[!UICONTROL addressExclusions]** )
* **[!UICONTROL Exclusion of domains]** ( **[!UICONTROL domainExclusions]** ).

在电子邮件分析期间，这些规则将收件人电子邮件地址与可投放性实例中管理的加密全局抑制列表中包含的禁止地址或域名进行比较。 如果存在匹配项，则不会向该收件人发送消息。

这是为了避免由于恶意活动(阻止列表尤其是使用Spamtrap)而被添加到中。 例如，如果使用Spamtrap通过您的一个Web窗体订阅，则会自动向该Spamtrap发送确认电子邮件，这会导致您的地址被自动添加到该阻止列表页面。

>[!NOTE]
>
>全局禁止列表中包含的地址和域名将被隐藏。 投放分析日志中只显示被排除的收件人数。

## 创建过滤规则 {#creating-a-filtering-rule}

您可以根据需要创建自己的过滤规则。 例如，您可以过滤新闻稿的目标群体，以便18岁以下的订阅者永远不会收到通信。

要创建过滤分类规则，请执行以下步骤：

1. 创建新分类规则。 有关创建分类规则的主要步骤，请参见 [此部分](../../sending/using/managing-typology-rules.md).

1. 选择 **[!UICONTROL Filtering]** 规则类型，然后指定所需的渠道。

1. 在 **[!UICONTROL Filtering criteria]** 选项卡上，选择 **[!UICONTROL Subscription]** 类别。

   ![](assets/typology_create-rule-subscription.png)

1. 在 **[!UICONTROL Explorer]** ，拖放 **[!UICONTROL Subscriber]** 节点添加到屏幕的主部分。

   ![](assets/typology_create-rule-subscriber.png)

1. 选择 **[!UICONTROL Age]** 字段，并定义筛选条件，以便订阅者的年龄在18岁或更高。

   ![](assets/typology_create-rule-age.png)

1. 在 **[!UICONTROL Typologies]** 选项卡，将此规则链接到分类。

   ![](assets/typology_create-rule-typology.png)

1. 确保在要使用的投放或投放模板中选择分类。 如需详细信息，请参阅[此部分](../../sending/using/managing-typologies.md#applying-typologies-to-messages)。

   ![](assets/typology_template.png)

每当在消息中使用此规则时，被视为未成年人的订阅者都将被自动排除。

## 配置筛选规则的定向上下文 {#configuring-filtering-rules-targeting-context}

Campaign Standard允许您配置  **定位** 和 **筛选** 维度，具体取决于您要定位的数据。

为此，请打开分类规则的属性，然后访问 **[!UICONTROL Advanced information]** 中。

默认情况下，会对 **[!UICONTROL Profiles]**. 例如，如果规则针对的是移动应用程序，则 **[!UICONTROL Filtering dimension]** 可更改为 **[!UICONTROL Subscriptions to an application]**.

![](assets/typology_rule-order_2.png)

## 限制筛选规则的适用性 {#restricting-the-applicability-of-a-filtering-rule}

您可以根据要发送的消息限制筛选规则的适用性。

1. 在分类规则的 **[!UICONTROL Application criteria]** 选项卡，取消选中 **[!UICONTROL Apply the rule on all deliveries]** 选项，默认情况下处于启用状态。

   ![](assets/typology_limit.png)

1. 使用查询编辑器定义过滤器。 例如，您只能对标签以给定单词开头或ID包含某些字母的消息应用规则。

   ![](assets/typology_limit-rule.png)

在这种情况下，规则仅应用于与定义的标准对应的消息。
