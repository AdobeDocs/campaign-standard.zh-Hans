---
title: 过滤规则
seo-title: 过滤规则
description: 过滤规则
seo-description: 使用过滤规则优化消息的受众。
page-status-flag: 从未激活
uuid: ed3eea62-3a47-4318-ae22-d82 aa857448 f
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: 使用字型规则
discoiquuid: 7ddaf36c-74e6-4501-b3 eb-3d03 f005 aa6
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Filtering rules{#filtering-rules}

过滤规则允许您根据查询中定义的条件(如已发送特定数量的电子邮件的隔离配置文件或配置文件)排除消息目标的一部分。

例如，您可以过滤Newsletter订阅者，以便不超过18岁的订户从不接收通信。

## Creating a filtering rule {#creating-a-filtering-rule}

1. Create a **Filtering** typology rule, one that can be applied on all communication channels.

   ![](assets/typology_create-rule.png)

1. In the **[!UICONTROL Filtering criteria]** tab, select the subscriptions in the **[!UICONTROL Subscription]** category.

   ![](assets/typology_create-rule-subscription.png)

1. In the **[!UICONTROL Explorer]** tab of the query editor, drag and drop the **[!UICONTROL Subscriber]** node into the main part of the screen.

   ![](assets/typology_create-rule-subscriber.png)

1. Select the **[!UICONTROL Age]** field and define the filtering conditions so that the age of the subscribers is 18 or above.

   ![](assets/typology_create-rule-age.png)

1. **[!UICONTROL Typologies]** 在选项卡中，将此规则链接到字型。

   ![](assets/typology_create-rule-typology.png)

1. 确保在要使用的交付模板中选择了相关字型。

   ![](assets/typology_template.png)

   >[!NOTE]
   >
   >To access the delivery templates, select **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** in the navigation menu, which can be accessed via the Adobe Campaign logo.

只要在消息中使用此规则，被视为未成年人的用户将被自动排除。

## Restricting the applicability of a filtering rule {#restricting-the-applicability-of-a-filtering-rule}

您可以根据要发送的消息限制过滤规则的适用性。

1. In the typology rule's **[!UICONTROL Application criteria]** tab, uncheck the **[!UICONTROL Apply the rule on all deliveries]** option, which is enabled by default.

   ![](assets/typology_limit.png)

1. 使用查询编辑器定义过滤器。例如，只能对标签以给定单词开头或ID包含特定字母的消息应用规则。

   ![](assets/typology_limit-rule.png)

在这种情况下，规则仅适用于与定义的条件相对应的消息。

## Default deliverability exclusion rules {#default-deliverability-exclusion-rules}

Two filtering rules are available by default: **[!UICONTROL Exclusion of addresses]** ( **[!UICONTROL addressExclusions]** ) and **[!UICONTROL Exclusion of domains]** ( **[!UICONTROL domainExclusions]** ). 在电子邮件分析过程中，这些规则将接收人电子邮件地址与在可交付实例中管理的加密的全局抑制列表中包含的地址或域名进行比较。如果存在匹配项，则消息不会发送给该收件人。

这是为了避免由于恶意活动而被列入黑名单，特别是使用垃圾邮件。例如，如果使用Spam陷通过某个Web表单订阅，则确认电子邮件会自动发送到该垃圾邮件，并且此结果会自动列入黑名单。

>[!NOTE]
>
>全局抑制列表中包含的地址和域名处于隐藏状态。仅在交付分析日志中指明被排除收件人的数量。

