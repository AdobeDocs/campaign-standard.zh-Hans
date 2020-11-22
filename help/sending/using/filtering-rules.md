---
solution: Campaign Standard
product: campaign
title: 筛选规则
description: 使用筛选规则优化消息的受众。
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 3%

---


# 筛选规则 {#filtering-rules}

过滤规则允许您根据查询中定义的条件排除邮件目标的一部分，如已发送一定数量电子邮件的隔离用户档案或用户档案。

## 默认筛选类型规则 {#default-filtering-typology-rules}

下表提供了有关现成过滤规则及其相关渠道的信息。

| 标签 | 渠道 | 说明 |
---------|----------|---------
| **[!UICONTROL Address not specified]** | 所有 | 排除没有指定地址（电子邮件、邮政地址等）的目标。 根据选定渠道)。 |
| **[!UICONTROL Address on denylist]** | 所有 | 不包括此中的阻止列表地址。 |
| **[!UICONTROL Duplicate]** | 所有 | 排除基于重复人口字段的 **[!UICONTROL Address]** 目标。 |
| **[!UICONTROL Exclude mobile applications]** | 移动应用程序 | 不包括与消息中定义的移动应用程序不匹配的应用程序订阅。 |
| **[!UICONTROL Exclude mobile applications for In-App]** | 应用程序内 | 不包括与消息（应用程序内模板）中定义的移动应用程序不匹配的应用程序订阅。 |
| **[!UICONTROL Exclude mobile applications for In-App broadcast]** | 应用程序内 | 不包括与消息中定义的移动应用程序不匹配的应用程序订阅（应用程序内广播模板） |
| **[!UICONTROL Exclude mobile applications for Push]** | 移动应用程序 | 不包括与消息中定义的移动应用程序不匹配的应用程序订阅（对于推送） |
| **[!UICONTROL Quarantined address]** | 所有 | 不包括隔离地址。 |
| **[!UICONTROL Target limited in size]** | 所有 | 检查投放是否达到最大目标大小。 适用于已激活“投放”选项的直邮投放期限。 |

除了这些默认过滤规则之外，还有两个排除规则：

* **[!UICONTROL Exclusion of addresses]** ( **[!UICONTROL addressExclusions]** )
* **[!UICONTROL Exclusion of domains]** ( **[!UICONTROL domainExclusions]** ).

在电子邮件分析期间，这些规则将收件人电子邮件地址与在可交付性实例中管理的加密全局禁止列表中包含的禁止地址或域名进行比较。 如果存在匹配项，则消息不会发送到该收件人。

这可以避免由于恶意活动阻止列表（特别是使用垃圾邮件陷阱）而添加到该。 例如，如果使用垃圾邮件陷阱通过您的某个Web表单进行订阅，则会自动向该垃圾邮件陷阱发送确认电子邮件，这会导致您的地址被自动添加到该阻止列表垃圾邮件。

>[!NOTE]
>
>全局禁止列表中包含的地址和域名将被隐藏。 在收件人分析日志中只指示被排除的投放数。

## Creating a filtering rule {#creating-a-filtering-rule}

您可以根据自己的需要创建自己的过滤规则。 例如，您可以过滤新闻稿的目标群，使18岁以下的订阅者永远不会收到通信。

要创建筛选类型规则，请执行以下步骤：

1. 创建新类型规则。 创建类型规则的主要步骤在此部 [分中详细介绍](../../sending/using/managing-typology-rules.md)。

1. 选择规 **[!UICONTROL Filtering]** 则类型，然后指定所需的渠道。

1. 在选 **[!UICONTROL Filtering criteria]** 项卡中，选择类别中的订阅 **[!UICONTROL Subscription]** 。

   ![](assets/typology_create-rule-subscription.png)

1. 在查询 **[!UICONTROL Explorer]** 编辑器的选项卡中，将节点拖 **[!UICONTROL Subscriber]** 放到屏幕的主要部分。

   ![](assets/typology_create-rule-subscriber.png)

1. 选择字 **[!UICONTROL Age]** 段并定义筛选条件，使订阅者的年龄在18岁或以上。

   ![](assets/typology_create-rule-age.png)

1. 在选项卡 **[!UICONTROL Typologies]** 中，将此规则链接到类型学。

   ![](assets/typology_create-rule-typology.png)

1. 确保在要使用的投放或投放模板中选择了类型。 如需详细信息，请参阅[此部分](../../sending/using/managing-typologies.md#applying-typologies-to-messages)。

   ![](assets/typology_template.png)

每当在消息中使用此规则时，将自动排除被视为未成年人的订阅者。

## 配置筛选规则的定位上下文 {#configuring-filtering-rules-targeting-context}

Campaign Standard允许您根 **据要** 目标 **的数据** ，配置定位和筛选维。

为此，请打开类型规则的属性，然后访问该 **[!UICONTROL Advanced information]** 部分。

By default, filtering is carried out on the **[!UICONTROL Profiles]**. 例如，如果规则针对移动应用程序，则可 **[!UICONTROL Filtering dimension]** 以将其更改为 **[!UICONTROL Subscriptions to an application]**。

![](assets/typology_rule-order_2.png)

## Restricting the applicability of a filtering rule {#restricting-the-applicability-of-a-filtering-rule}

可以根据要发送的消息限制过滤规则的适用性。

1. 在类型规则的选 **[!UICONTROL Application criteria]** 项卡中，取消选 **[!UICONTROL Apply the rule on all deliveries]** 中选项，该选项默认处于启用状态。

   ![](assets/typology_limit.png)

1. 使用查询编辑器定义筛选器。 例如，您只能对标签开始带有给定字词或ID包含某些字母的邮件应用规则。

   ![](assets/typology_limit-rule.png)

在这种情况下，该规则仅应用于与定义的条件对应的消息。
