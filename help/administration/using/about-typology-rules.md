---
title: 关于字型规则
seo-title: 关于字型规则
description: 关于字型规则
seo-description: 了解多态规则在Adobe Campaign中的工作原理。
page-status-flag: 从未激活
uuid: a98ebc36-172d-4f46-b6 ee-b2636 a1007 c9
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: 使用字型规则
discoiquuid: 2590d94c-51ef-4c0f-b1 ec-c2837 e94 da40
context-tags: typology，概述；typology规则，main；typology规则，概述
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 5e5532c0769fe33016eaee994bdaae9c70a7eaa5

---


# About typology rules{#about-typology-rules}

字节数是在消息分析阶段执行的一组规则，它允许目标、内容和配置以下元素进行验证：主题、URL、图像、取消订阅链接、校样大小等。

在Adobe Campaign中，每条消息都包含一个指向字型的链接。This link is defined in the advanced parameters of the delivery template's properties (for more on this, refer to the [Preparation](../../administration/using/configuring-email-channel.md#preparation) section).

>[!NOTE]
>
>每条消息只能分配给一个字型。

For each typology, the **[!UICONTROL Typology rules]** section lists the set of rules for this typology.

![](assets/typology_typo-rule-list.png)

## Managing typologies {#managing-typologies}

默认情况下，应用程序中有多个字节数。根据您的需求，您可以创建自己的字体或修改现有字体。

1. Access the **[!UICONTROL List of typologies]** from the **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** menu.
1. 选择字体以修改其内容和属性或创建新属性。

   ![](assets/typology_list.png)

1. 定义字型类型。类型可为标准或筛选字型。
1. Add the typology rules you need using the **[!UICONTROL Add an element]** button or remove the ones you do not want to use.

   您可以修改为给定类型应用规则的顺序。为此，移动元素以修改它们在屏幕上的显示顺序。随后会自动重新计算执行顺序对应的数字。The rule application mode is presented in the [Typology rules execution order](../../administration/using/about-typology-rules.md#typology-rules-execution-order) section.

   在此屏幕上显示的规则可在只读模式下访问。

您的字型可随时使用。您可以在消息属性或消息模板属性中选择它。

>[!NOTE]
>
>**[!UICONTROL IP affinity]** 该字段允许您根据配置管理相似性。它们在实例的配置文件中定义。如果您要使用相似性，请与管理员联系。

## Typology rules {#typology-rules}

Typology规则是在消息准备过程中应用的业务规则。它们用于检查消息是否有效并符合质量标准。他们还检查目标受众的每个成员是否有资格收到此消息。

Typology rules are available under the **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** &gt; **[!UICONTROL Typology rules]** menu.

有两种类型的规则：

* **过滤** 规则：允许您根据查询中定义的条件(如已发送特定数量的电子邮件的隔离配置文件或配置文件)排除消息目标的一部分。See [Filtering rules](../../administration/using/filtering-rules.md).
* **疲劳** 规则：允许您定义每个配置文件的最大消息数以避免过度征求信息。See [Fatigue rules](../../administration/using/fatigue-rules.md).
* **控制** 规则：允许用户在发送消息之前检查其有效性和质量，如字符显示、SMS消息大小、地址格式等。See [Control rules](../../administration/using/control-rules.md).

字型规则只能应用于一个渠道或所有渠道。

![](assets/typology_channel.png)

In the **[!UICONTROL Properties]** of a typology rule, you can set its execution order. 必须应用多个规则时，每个规则的执行顺序决定要处理的规则。For more on this, refer to the [Typology rules execution order](../../administration/using/about-typology-rules.md#typology-rules-execution-order) section.

![](assets/typology_rule-active.png)

A typology rule can be deactivated through its **[!UICONTROL Properties]** if you do not want the rule to be applied at the moment that the messages concerned by the rule are analyzed.

![](assets/typology_rule-order.png)

**[!UICONTROL Targeting context]** 在类别中，您可以根据要定位的数据选择 **定位维度** 和 **过滤维度** 。

By default, filtering is carried out on the **[!UICONTROL Profiles]**. For example, if the rule is aimed at a mobile application, the **[!UICONTROL Filtering dimension]** can be changed to **[!UICONTROL Subscriptions to an application]**.

![](assets/typology_rule-order_2.png)

## Typology rules execution order {#typology-rules-execution-order}

类型规则按定位、分析和消息个性化阶段指定的顺序执行。

在标准操作模式下，规则按以下顺序应用：

1. 控制规则(如果在定位开始时应用)。
1. 过滤规则：

   * 用于地址资格的本机应用程序规则：定义的地址/未验证地址/黑名单地址/统一地址/地址质量。
   * 过滤用户定义的规则。

1. 控制规则(如果在定位结束时应用)。
1. 控制规则(如果在个性化开始时应用)。
1. 控制规则(如果在个性化时应用)。

但是，您可以在每个类型中调整相同类型规则的执行顺序。实际上，当在同一消息处理阶段执行多个规则时，您可以选择应用它们的顺序。

例如，将在执行订单的过滤规则之前执行执行顺序为20的过滤规则，其执行顺序位于30处。
