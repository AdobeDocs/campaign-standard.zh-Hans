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
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 3%

---

# 筛选规则 {#filtering-rules}

利用筛选规则，可根据查询中定义的条件排除部分消息目标，例如已隔离的用户档案或已向其发送了一定数量电子邮件的用户档案。

## 默认筛选类型规则 {#default-filtering-typology-rules}

下表提供了有关现成筛选规则及其相关渠道的信息。

| 标签 | 渠道 | 说明 |
| ---------|----------|---------|
| **[!UICONTROL Address not specified]** | 全部 | 不包括未指定地址（电子邮件、邮政地址等）的目标人群。 （根据所选渠道）。 |
| **[!UICONTROL Address on denylist]** | 全部 | 排除阻止列表上的地址。 |
| **[!UICONTROL Duplicate]** | 全部 | 根据目标群体排除重复项 **[!UICONTROL Address]** 字段。 |
| **[!UICONTROL Exclude mobile applications]** | 移动应用程序 | 排除与消息中定义的移动应用程序不匹配的应用程序订阅。 |
| **[!UICONTROL Exclude mobile applications for In-App]** | 应用程序内 | 排除与消息中定义的移动应用程序不匹配的应用程序订阅（应用程序内模板）。 |
| **[!UICONTROL Exclude mobile applications for In-App broadcast]** | 应用程序内 | 排除与消息中定义的移动应用程序不匹配的应用程序订阅（应用程序内广播模板） |
| **[!UICONTROL Exclude mobile applications for Push]** | 移动应用程序 | 排除与消息中定义的移动应用程序不匹配的应用程序订阅（用于推送） |
| **[!UICONTROL Quarantined address]** | 全部 | 不包括隔离的地址。 |
| **[!UICONTROL Target limited in size]** | 全部 | 检查是否已达到目标的最大投放大小。 适用于激活了“投放限制”选项的直邮投放。 |

除了这些默认筛选规则之外，还提供两个排除规则：

* **[!UICONTROL Exclusion of addresses]** ( **[!UICONTROL addressExclusions]** )
* **[!UICONTROL Exclusion of domains]** ( **[!UICONTROL domainExclusions]** )。

在电子邮件分析期间，这些规则将收件人电子邮件地址与包含在可投放性实例中管理的加密全局禁止列表中的禁止地址或域名进行比较。 如果存在匹配项，则不会将该消息发送给该收件人。

列入阻止列表这是为了避免由于恶意活动（特别是使用Spamtrap）而添加到。 列入阻止列表例如，如果使用Spamtrap通过某个Web窗体进行订阅，则会自动向该Spamtrap发送确认电子邮件，这会导致您的地址自动添加到中。

>[!NOTE]
>
>全局隐藏列表中包含的地址和域名是隐藏的。 投放分析日志中仅指示排除的收件人的数量。

## 创建筛选规则 {#creating-a-filtering-rule}

您可以根据需要创建自己的筛选规则。 例如，您可以筛选新闻稿的目标群体，这样18岁以下的订阅者就不会收到通信。

要创建筛选分类规则，请执行以下步骤：

1. 创建新的分类规则。 有关创建分类规则的主要步骤，请参见 [本节](../../sending/using/managing-typology-rules.md).

1. 选择 **[!UICONTROL Filtering]** 规则类型，然后指定所需的渠道。

1. 在 **[!UICONTROL Filtering criteria]** 选项卡中，选择订阅 **[!UICONTROL Subscription]** 类别。

   ![](assets/typology_create-rule-subscription.png)

1. 在 **[!UICONTROL Explorer]** 查询编辑器的选项卡，拖放 **[!UICONTROL Subscriber]** 节点放入屏幕的主部分。

   ![](assets/typology_create-rule-subscriber.png)

1. 选择 **[!UICONTROL Age]** 字段并定义筛选条件，使订阅者的年龄小于18岁。

   ![](assets/typology_create-rule-age.png)

1. 在 **[!UICONTROL Typologies]** 选项卡，将此规则链接到分类。

   ![](assets/typology_create-rule-typology.png)

1. 确保在要使用的投放或投放模板中选择分类。 如需详细信息，请参阅[此小节](../../sending/using/managing-typologies.md#applying-typologies-to-messages)。

   ![](assets/typology_template.png)

无论何时在消息中使用此规则，都将自动排除被视为未成年人的订阅者。

## 配置过滤规则的定位上下文 {#configuring-filtering-rules-targeting-context}

Campaign Standard允许您配置  **定位** 和 **正在筛选** 根据要定位的数据使用的维度。

为此，请打开分类规则的属性，然后访问 **[!UICONTROL Advanced information]** 部分。

默认情况下，会对 **[!UICONTROL Profiles]**. 例如，如果规则针对移动应用程序，则 **[!UICONTROL Filtering dimension]** 可更改为 **[!UICONTROL Subscriptions to an application]**.

![](assets/typology_rule-order_2.png)

## 限制筛选规则的适用性 {#restricting-the-applicability-of-a-filtering-rule}

您可以根据要发送的消息限制筛选规则的适用性。

1. 在分类规则的 **[!UICONTROL Application criteria]** 选项卡，取消选中 **[!UICONTROL Apply the rule on all deliveries]** 选项，默认情况下会启用此选项。

   ![](assets/typology_limit.png)

1. 使用查询编辑器定义过滤器。 例如，只能对标签以给定单词开头或ID包含特定字母的消息应用规则。

   ![](assets/typology_limit-rule.png)

在这种情况下，该规则仅适用于与定义的标准对应的消息。
