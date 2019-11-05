---
title: 关于类型学规则
description: 了解排版规则在Adobe Campaign中的工作方式。
page-status-flag: 从未激活
uuid: a98ebc36-172d-4f46-b6ee-b2636a1007c9
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 管理
content-type: 参考
topic-tags: 排版规则
discoiquuid: 2590d94c-51ef-4c0f-b1ec-c2837e94da40
context-tags: 类型学，概述；类型学规则，主要；类型学规则，概述
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 关于类型学规则{#about-typology-rules}

排版是在消息分析阶段执行的一组规则，允许验证以下元素的目标、内容和配置：主题、URL、图像、取消订阅链接、校样大小等。

在Adobe Campaign中，每条消息都包含指向排版的链接。 此链接在交付模板属性的高级参数中定义(有关详细信息，请参阅准备 [部分](../../administration/using/configuring-email-channel.md#preparation) )。

>[!NOTE]
>
>每条消息只能分配一个类型学。

对于每种类型学， **[!UICONTROL Typology rules]** 该部分列出了此类型学的一组规则。

![](assets/typology_typo-rule-list.png)

## 管理类型 {#managing-typologies}

默认情况下，应用程序中存在几种类型。 根据您的需求，您可以创建自己的字体或修改现有的字体。

1. 从&gt; **[!UICONTROL List of typologies]** &gt;菜单访 **[!UICONTROL Administration]** 问 **[!UICONTROL Channels]** 该 **[!UICONTROL Typologies]** 选项。
1. 选择一种类型学以修改其内容和属性或创建新的类型学。

   ![](assets/typology_list.png)

1. 定义类型。 类型可以是标准或筛选类型。
1. 使用按钮添加您需要的排 **[!UICONTROL Add an element]** 版规则，或删除您不想使用的规则。

   您可以修改规则应用于给定类型学的顺序。 为此，请移动元素以修改它们在屏幕上的显示顺序。 然后自动地重新计算与执行顺序相对应的数字。 规则应用模式在“类型学规则” [执行顺序部分中显示](#typology-rules-execution-order) 。

   此屏幕上显示的规则可以以只读模式访问。

您的排版已准备好使用。 您可以在消息属性或消息模板属性中选择它。

>[!NOTE]
>
>该字 **[!UICONTROL IP affinity]** 段允许您根据配置管理相关性。 这些定义在实例的配置文件中。 如果要使用相关性，请与管理员联系。

## 排版规则 {#typology-rules}

类型学规则是在消息准备过程中应用的业务规则。 它们用于检查消息是否有效并满足您的质量标准。 他们还检查目标受众的每个成员是否有资格接收消息。

排版规则位于 **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** &gt;菜 **[!UICONTROL Typology rules]** 单下。

规则有两种类型：

* **筛选规则** :允许您根据在查询中定义的条件（如已发送特定数量电子邮件的隔离配置文件或配置文件）排除邮件目标的一部分。 请参阅 [筛选规则](../../administration/using/filtering-rules.md)。
* **疲劳规则** :允许您为每个配置文件定义最大消息数，以避免过度征求消息。 请参阅 [疲劳规则](../../administration/using/fatigue-rules.md)。
* **控制规则** :允许用户在发送消息之前检查消息的有效性和质量，如字符显示、SMS消息大小、地址格式等。 请参阅 [控制规则](../../administration/using/control-rules.md)。

排版规则只能应用于一个渠道或所有渠道。

![](assets/typology_channel.png)

在排 **[!UICONTROL Properties]** 版规则中，您可以设置其执行顺序。 当必须应用多个规则时，每个规则的执行顺序决定要首先处理的规则。 有关详细信息，请参阅“排 [版规则执行顺序](#typology-rules-execution-order) ”部分。

![](assets/typology_rule-active.png)

如果不希望在分析规则所关 **[!UICONTROL Properties]** 注的消息时应用该规则，则可以通过其取消激活字体规则。

![](assets/typology_rule-order.png)

在类 **[!UICONTROL Targeting context]** 别中，您可以根据要定 ******** 位的数据选择定位维和筛选维。

默认情况下，对进行筛选 **[!UICONTROL Profiles]**。 例如，如果规则针对移动应用程序，则可 **[!UICONTROL Filtering dimension]** 以将其更改为 **[!UICONTROL Subscriptions to an application]**。

![](assets/typology_rule-order_2.png)

## 排版规则执行顺序 {#typology-rules-execution-order}

排版规则按在定位、分析和消息个性化阶段中指定的顺序执行。

在标准操作模式下，这些规则按以下顺序应用：

1. 控制规则（如果在定位开始时应用它们）。
1. 筛选规则:

   * 地址资格的本机应用程序规则：定义的地址／未验证的地址／列入黑名单的地址／隔离地址／地址质量。
   * 过滤用户定义的规则。

1. 控制规则（如果在定位结束时应用它们）。
1. 控制规则（如果在个性化开始时应用它们）。
1. 控制规则（如果在个性化结束时应用它们）。

但是，您可以在每种类型学中调整相同类型规则的执行顺序。 事实上，当在同一消息处理阶段执行多个规则时，您可以选择应用这些规则的顺序。

例如，执行顺序位于第20位的过滤规则将在执行顺序位于第30位的过滤规则之前执行。
