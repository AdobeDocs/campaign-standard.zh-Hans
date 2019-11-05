---
title: 筛选规则
description: 使用过滤规则优化消息的受众。
page-status-flag: 从未激活
uuid: ed3eea62-3a47-4318-ae22-d82aa857448f
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 管理
content-type: 参考
topic-tags: 排版规则
discoiquuid: 7ddaf36c-74e6-4501-b3eb-3d03f005aaa6
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 筛选规则{#filtering-rules}

过滤规则允许您根据在查询中定义的条件排除消息目标的一部分，如已发送特定数量电子邮件的隔离配置文件或配置文件。

例如，您可以过滤新闻稿订阅者，使18岁以下的订阅者永远不会收到通信。

## 创建筛选规则 {#creating-a-filtering-rule}

1. 创建可 **应用于所有通信渠道** 的过滤类型规则。

   ![](assets/typology_create-rule.png)

1. 在选项卡 **[!UICONTROL Filtering criteria]** 中，选择类别中的订 **[!UICONTROL Subscription]** 阅。

   ![](assets/typology_create-rule-subscription.png)

1. 在查 **[!UICONTROL Explorer]** 询编辑器的选项卡中，将节点拖 **[!UICONTROL Subscriber]** 放到屏幕的主要部分。

   ![](assets/typology_create-rule-subscriber.png)

1. 选择字 **[!UICONTROL Age]** 段并定义过滤条件，使订阅者的年龄在18岁或以上。

   ![](assets/typology_create-rule-age.png)

1. 在选项 **[!UICONTROL Typologies]** 卡中，将此规则链接到类型学。

   ![](assets/typology_create-rule-typology.png)

1. 确保在要使用的交付模板中选择了相关的类型。

   ![](assets/typology_template.png)

   >[!NOTE]
   >
   >要访问交付模板，请在导 **[!UICONTROL Resources]** 航 **[!UICONTROL Templates]** 菜单中选择&gt;，可通过Adobe Campaign徽标访问该菜单。

每当在消息中使用此规则时，被视为未成年人的订阅者将被自动排除。

## 限制筛选规则的适用性 {#restricting-the-applicability-of-a-filtering-rule}

可以根据要发送的消息限制过滤规则的适用性。

1. 在排版规则的选项 **[!UICONTROL Application criteria]** 卡中，取消选 **[!UICONTROL Apply the rule on all deliveries]** 中此选项，该选项默认处于启用状态。

   ![](assets/typology_limit.png)

1. 使用查询编辑器定义筛选器。 例如，您只能对标签以给定单词开头或其ID包含某些字母的消息应用该规则。

   ![](assets/typology_limit-rule.png)

在这种情况下，该规则仅应用于与定义的条件相对应的消息。

## 默认可交付性排除规则 {#default-deliverability-exclusion-rules}

默认情况下有两种筛选规则： **[!UICONTROL Exclusion of addresses]** ( **[!UICONTROL addressExclusions]** )和 **[!UICONTROL Exclusion of domains]** ( **[!UICONTROL domainExclusions]** )。 在电子邮件分析过程中，这些规则将收件人电子邮件地址与包含在可交付性实例中管理的加密全局禁止列表中的禁止地址或域名进行比较。 如果存在匹配项，则不会向该收件人发送消息。

这可以避免由于恶意活动（特别是使用Spamtrap）而被列入黑名单。 例如，如果使用Spamtrap通过您的某个Web表单进行订阅，则会自动向该Spamtrap发送确认电子邮件，这会导致您的地址自动列入黑名单。

>[!NOTE]
>
>包含在全局隐藏列表中的地址和域名是隐藏的。 在分发分析日志中只显示被排除的收件人数。

