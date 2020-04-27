---
title: 管理类型规则
description: 了解如何使用类型规则。
page-status-flag: never-activated
uuid: a98ebc36-172d-4f46-b6ee-b2636a1007c9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 2590d94c-51ef-4c0f-b1ec-c2837e94da40
context-tags: typology,overview;typologyRule,main;typologyRule,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ba1fcca02ce9582d85e57bde815ccf3f551ac7a3

---


# 管理类型规则 {#managing-typology-rules}

## 关于类型学规则 {#about-typology-rules}

类型规则是允许您在发送邮件之前对邮件执行检查和过滤的业务规则。 可用的类型规则类型包括：

* **筛选规则** :此类型的规则允许您根据查询中定义的条件排除消息目标的一部分，例如已发送特定数量电子邮件的隔离用户档案或用户档案。 如需详细信息，请参阅[此部分](../../sending/using/filtering-rules.md)。

* **疲劳规则** :此类规则允许您为每个用户档案定义最大消息数，以避免过度征求消息。 如需详细信息，请参阅[此部分](../../sending/using/fatigue-rules.md)。

* **控制规则** :这种规则允许用户在发送消息之前检查消息的有效性和质量，如字符显示、SMS消息大小、地址格式等。 如需详细信息，请参阅[此部分](../../sending/using/control-rules.md)。

类型规则位于 **[!UICONTROL Administration]** > > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** >菜 **[!UICONTROL Typology rules]** 单下。

默认情况下，可以使用多个现成 **的过****滤和控** 制类型规则。 过滤规则和控制规 [则部分详细介绍](../../sending/using/fatigue-rules.md)[了这些规则](../../sending/using/control-rules.md) 。

根据您的需要，您可以修改现有类型规则或创建新，但规则除外， **[!UICONTROL Control]** 这些规则是只读的，不能修改。

## 创建类型规则 {#creating-a-typology-rule}

创建类型规则的主要步骤如下：

1. 访问/ **[!UICONTROL Administration]** / **[!UICONTROL Channels]** /菜 **[!UICONTROL Typologies]** 单，然后单击 **[!UICONTROL Typology rules]****[!UICONTROL Create]**。

   ![](assets/typology_create-rule.png)

1. 输入类型 **[!UICONTROL Label]**&#x200B;学，然后指 **[!UICONTROL Channel]** 定应用规则的类型。

   ![](assets/typology-rule-label.png)

1. 指定类型规则 **[!UICONTROL Type]**，然后根据需要配置它。 请注意，类型规则配置因类型而异。 有关详细信息，请参阅“筛选 **[规则](../../sending/using/filtering-rules.md)**”(Filtering rules**[)](../../sending/using/fatigue-rules.md)** 和“疲劳规则”(Fatiuge rules)部分。

1. 选择要包含新规则的类型。 要执行此操作，请选择选 **[!UICONTROL Typologies]** 项卡，然后单击 **[!UICONTROL Create element]** 按钮。

   ![](assets/typology-typologies-tab.png)

1. 选择所需的类型学，然后单击 **[!UICONTROL Confirm]**。

   ![](assets/typology-link.png)

1. 选择所有类型后，单击以 **[!UICONTROL Create]** 确认创建类型规则。

## 类型规则执行订单 {#typology-rules-execution-order}

类型规则按在定位、分析和消息个性化阶段指定的顺序执行。

在标准操作模式下，这些规则按以下顺序应用：

1. 控制规则(如果在定位开始应用这些规则)。
1. 筛选规则:

   * 地址资格的本机应用程序规则：定义的地址／未验证的地址/已列入黑名单地址／隔离的地址／地址质量。
   * 过滤用户定义的规则。

1. 控制规则（如果在定位结束时应用它们）。
1. 控制规则(如果在个性化开始应用这些规则)。
1. 控制规则（如果在个性化结束时应用它们）。

但是，您可以在每种类型学中调整相同类型规则的执行顺序。 事实上，当在同一消息处理阶段执行多个规则时，您可以选择应用这些规则的顺序。

例如，执行顺序位于第20位的过滤规则将在执行顺序位于第30位的过滤规则之前执行。

在类型规则 **[!UICONTROL Properties]** 中，您可以设置其执行顺序。 当必须应用多个规则时，每个规则的执行顺序决定要首先处理的规则。 有关详细信息，请参阅 [类型规则执行订单部分](#typology-rules-execution-order) 。

![](assets/typology_rule-active.png)

如果您不希望在分析规则所关 **[!UICONTROL Properties]** 注的消息时应用该规则，则可以通过其取消激活类型规则。

![](assets/typology_rule-order.png)