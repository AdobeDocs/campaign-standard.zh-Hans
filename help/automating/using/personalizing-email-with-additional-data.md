---
title: 个性化包含其他数据的电子邮件
description: 此用例介绍如何向查询添加不同类型的附加数据，并将其用作电子邮件中的个性化字段。
page-status-flag: never-activated
uuid: b3c629fa-370e-481c-b347-fcf9f5a5e847
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 8d46ce28-0101-4f13-865a-2208ed6d6139
context-tags: query,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2d994d85f126951215f1227301599c554c1f12c8
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 0%

---


# 个性化包含其他数据的电子邮件 {#example--personalizing-an-email-with-additional-data}

以下示例说明如何向查询添加不同类型的附加数据，以及如何在电子邮件中将其用作个性化字段。 有关如何丰富活动所针对的数据的详 **[!UICONTROL Query]** 细信息，请 [参阅本节](../../automating/using/query.md#enriching-data)。

在此示例中， [使用自定](../../developing/using/data-model-concepts.md) 义资源：

* 扩 **展用户档案** 资源以添加一个字段，该字段允许保存每个用户档案的忠诚度点。
* 创 **建事务** 资源，并标识用户档案在数据库中执行的所有购买。 系统会为每笔交易保存购买的日期、价格和产品。
* 已创 **建产品** 资源，并引用可供购买的产品。

目标是向至少保存了一个事务的用户档案发送电子邮件。 通过此电子邮件，客户将收到上次执行交易的提醒，以及所有交易的概述： 已购买的产品数量、总支出，提醒已累计的忠诚度积分总数。

工作流如下所示：

![](assets/enrichment_example1.png)

1. 添加 [查询](../../automating/using/query.md) 活动，该目标允许您已执行至少一项事务的用户档案。

   ![](assets/enrichment_example2.png)

   在查询的选 **[!UICONTROL Additional data]** 项卡中，定义要在最终电子邮件中显示的不同数据：

   * 与忠诚点对应 **的用户档案** 维的简单字段。 请参阅添 [加简单字段](../../automating/using/query.md#adding-a-simple-field) 。
   * 基于事务处理收集的两个聚合: 购买的产品数和支出总额。 您可以使用“计数” **[!UICONTROL Data]** 和“总计”聚合从聚合配置窗口的选 **项卡** 中添加它们 **** 。 请参阅添 [加聚合部分](../../automating/using/query.md#adding-an-aggregate) 。
   * 返回已用金额、日期和上次生效事务的产品的集合。

      为此，您必须添加要从集合配置窗口的选项卡中 **[!UICONTROL Data]** 显示的不同字段。

      要仅返回最近的事务，您必须为输入“1”，并 **[!UICONTROL Number of lines to return]** 从选项卡中对集合的“日 **期** ”字段应用降序 **[!UICONTROL Sort]** 排序。

      请参阅添加 [集合和对其](../../automating/using/query.md#adding-a-collection) 他 [数据进行排序](../../automating/using/query.md#sorting-additional-data) 。
   ![](assets/enrichment_example4.png)

   如果要检查活动的出站过渡是否正确传输数据，请首次开始工作流(不包括 **[!UICONTROL Email delivery]** 活动)并打开查询的出站过渡。

   ![](assets/enrichment_example5.png)

1. 添加电子 [邮件投放](../../automating/using/email-delivery.md) 活动。 在电子邮件内容中，插入与查询中计算的个性化字段相对应的。 您可以通过个性化字段资源 **[!UICONTROL Additional data (targetData)]** 管理器的链接找到它。

   ![](assets/enrichment_example3.png)

您的工作流现在可以执行。 查询中的目标用户档案将收到一封个性化电子邮件，其中包含从其交易中计算的数据。
