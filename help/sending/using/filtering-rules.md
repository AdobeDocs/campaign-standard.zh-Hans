---
title: 筛选规则
description: 使用筛选规则优化消息的受众。
page-status-flag: never-activated
uuid: ed3eea62-3a47-4318-ae22-d82aa857448f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 7ddaf36c-74e6-4501-b3eb-3d03f005aaa6
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ec0af8c06e36f51ddaf6e3d4190fa6acd56d2da6

---


# 筛选规则 {#filtering-rules}

过滤规则允许您根据查询中定义的条件排除消息目标的一部分，例如已发送特定数量电子邮件的隔离用户档案或用户档案。

## 默认筛选类型规则 {#default-filtering-typology-rules}

下表提供了有关现成过滤规则及其相关渠道的信息。

| 标签 | 渠道 | 说明 |
---------|----------|---------|---------
| **[!UICONTROL Address not specified]** | 所有 | 不包括没有指定地址（电子邮件、邮政地址等）的目标。 根据选定的渠道)。 |
| **[!UICONTROL Blacklisted address]** | 所有 | 不包括已列入黑名单地址。 |
| **[!UICONTROL Duplicate]** | 所有 | 不包括基于重复人口字段的目标 **[!UICONTROL Address]** 数据。 |
| **[!UICONTROL Exclude mobile applications]** | 移动应用程序 | 不包括与消息中定义的移动应用程序不匹配的应用程序订阅。 |
| **[!UICONTROL Exclude mobile applications for In-App]** | 应用程序内 | 不包括与消息（应用程序内模板）中定义的移动应用程序不匹配的应用程序订阅。 |
| **[!UICONTROL Exclude mobile applications for In-App broadcast]** | 应用程序内 | 不包括与消息中定义的移动应用程序不匹配的应用程序订阅（应用程序内广播模板） |
| **[!UICONTROL Exclude mobile applications for Push]** | 移动应用程序 | 不包括与消息中定义的移动应用程序不匹配的应用程序订阅（针对推送） |
| **[!UICONTROL Quarantined address]** | 所有 | 不包括隔离地址。 |
| **[!UICONTROL Target limited in size]** | 所有 | 检查投放是否达到最大目标大小。 适用于激活了“投放期限”选项的直邮投放。 |

除了这些默认过滤规则之外，还有两个排除规则：

* **[!UICONTROL Exclusion of addresses]** ( **[!UICONTROL addressExclusions]** )
* **[!UICONTROL Exclusion of domains]** ( **[!UICONTROL domainExclusions]** ).

在电子邮件分析期间，这些规则将收件人电子邮件地址与包含在可交付性实例中管理的加密全局禁止列表中的禁止地址或域名进行比较。 如果存在匹配项，则消息不会发送到该收件人。

这是为了避免由于恶意活动（特别是使用Spamtrap）而已列入黑名单。 例如，如果使用Spamtrap通过您的某个Web表单进行订阅，则会自动向该Spamtrap发送确认电子邮件，这会导致您的地址自动已列入黑名单。

>[!NOTE]
>
>包含在全局抑制列表中的地址和域名是隐藏的。 在投放收件人日志中仅指示被排除的分析数。

## 创建筛选规则 {#creating-a-filtering-rule}

您可以根据自己的需要创建自己的过滤规则。 例如，您可以过滤新闻稿的目标人口，使18岁以下的订阅者永远不会收到通信。

要创建筛选类型规则，请执行以下步骤：

1. 创建新类型规则。 创建类型规则的主要步骤在本节中有 [详细介绍](../../sending/using/managing-typology-rules.md)。

1. 选择规 **[!UICONTROL Filtering]** 则类型，然后指定所需的渠道。

1. 在“ **[!UICONTROsL筛选条件]** ”选项卡中，选择 **[!UICONTROL Subscription]** 类别。

   ![](assets/typology_create-rule-subscription.png)

1. 在查询编 **[!UICONTROL Explorer]** 辑器的选项卡中，将节点拖 **[!UICONTROL Subscriber]** 放到屏幕的主要部分。

   ![](assets/typology_create-rule-subscriber.png)

1. 选择字 **[!UICONTROL Age]** 段并定义过滤条件，使订阅者的年龄在18岁或以上。

   ![](assets/typology_create-rule-age.png)

1. 在选项 **[!UICONTROL Typologies]** 卡中，将此规则链接到类型学。

   ![](assets/typology_create-rule-typology.png)

1. 确保在要使用的投放或投放模板中选择了类型学。 如需详细信息，请参阅[此部分](../../sending/using/managing-typologies.md#applying-typologies-to-messages)。

   ![](assets/typology_template.png)

每当在消息中使用此规则时，被视为未成年人的订阅者将被自动排除。

## 配置筛选规则的定位上下文 {#configuring-filtering-rules-targeting-context}

Campaign Standard允许您根据要 **目标的数据** ，将定位和 **** 筛选维配置为使用。

为此，请打开类型规则的属性，然后访问该部 **[!UICONTROL Advanced information]** 分。

默认情况下，对进行筛选 **[!UICONTROL Profiles]**。 例如，如果规则针对移动应用程序，则可 **[!UICONTROL Filtering dimension]** 以将其更改为 **[!UICONTROL Subscriptions to an application]**。

![](assets/typology_rule-order_2.png)

## 限制筛选规则的适用性 {#restricting-the-applicability-of-a-filtering-rule}

可以根据要发送的消息限制过滤规则的适用性。

1. 在类型规则的选 **[!UICONTROL Application criteria]** 项卡中，取消选 **[!UICONTROL Apply the rule on all deliveries]** 中选项，该选项默认处于启用状态。

   ![](assets/typology_limit.png)

1. 使用查询编辑器定义过滤器。 例如，您只能对标签开始为给定单词或其ID包含某些字母的消息应用该规则。

   ![](assets/typology_limit-rule.png)

在这种情况下，该规则仅应用于与定义的条件相对应的消息。
