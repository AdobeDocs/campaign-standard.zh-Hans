---
title: 使用附加数据个性化电子邮件
description: 此使用案例說明如何將不同型別的其他資料新增到查詢中，並作為電子郵件中的個人化欄位使用。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: query,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: b207dc73-03dc-4f25-95e5-573e4b4bce54
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 86%

---

# 使用附加数据个性化电子邮件 {#example--personalizing-an-email-with-additional-data}

以下示例说明了如何向查询添加不同类型的附加数据，以及如何在电子邮件中将其用于个性化字段。如需如何豐富鎖定目標的資料的詳細資訊， **[!UICONTROL Query]** 活動，請參閱 [本節](../../automating/using/query.md#enriching-data).

在本例中，使用[自定义资源](../../developing/using/data-model-concepts.md)：

* 扩展了&#x200B;**用户档案**&#x200B;资源以添加字段，以便保存每个用户档案的会员积分。
* 创建了&#x200B;**交易**&#x200B;资源，并确定了数据库中的用户档案执行的所有购买。保存了每笔交易的购买日期、价格和产品。
* 创建了&#x200B;**产品**&#x200B;资源，并引用了可供购买的产品。

其目标是向至少保存了一次交易的用户档案发送电子邮件。通过此电子邮件，客户将收到上次执行交易的提醒及其所有交易的概况：已购买的产品数量、总花费，累计会员积分提醒。

其工作流如下所示：

![](assets/enrichment_example1.png)

1. 新增 [查詢](../../automating/using/query.md) 活動，可讓您定位已執行至少一個交易的設定檔。

   ![](assets/enrichment_example2.png)

1. 在查询的 **[!UICONTROL Additional data]** 选项卡中，定义要在最终电子邮件中显示的各种数据：

   * 与会员积分相对应的&#x200B;**用户档案**&#x200B;维度的简单字段。请参阅[添加简单字段](../../automating/using/query.md#adding-a-simple-field)。
   * 基于交易集合的两个聚合：购买的产品数和总花费金额。您可以使用 **Count** 和 **Sum** 聚合，从聚合配置窗口的 **[!UICONTROL Data]** 选项卡中添加它们。请参阅[添加聚合](../../automating/using/query.md#adding-an-aggregate)一节。
   * 集合返回的项包括已花费的金额、日期和上次交易生效的产品。

      要实现此目的，您必须从集合配置窗口的 **[!UICONTROL Data]** 选项卡添加要显示的各个字段。

      要仅返回最近的一次交易，您必须在 **[!UICONTROL Number of lines to return]** 中输入“1”，并在 **[!UICONTROL Sort]** 选项卡中对集合的 **Date** 字段应用降序排序。

      请参阅[添加集合](../../automating/using/query.md#adding-a-collection)和[为附加数据排序](../../automating/using/query.md#sorting-additional-data)。
   ![](assets/enrichment_example4.png)

1. 如果要检查活动的叫客过渡是否正确传输了数据，请第一时间启动工作流（不包括 **[!UICONTROL Email delivery]** 活动）并打开查询的叫客过渡。

   ![](assets/enrichment_example5.png)

1. 新增 [電子郵件傳遞](../../automating/using/email-delivery.md) 活動。 在电子邮件内容中，插入与查询中所计算数据相对应的个性化字段。您可以通过个性化字段资源管理器的 **[!UICONTROL Additional data (targetData)]** 链接找到它。

   ![](assets/enrichment_example3.png)

您的工作流现已准备就绪。查询中的所定向用户档案将收到一封个性化电子邮件，其中包含根据其交易计算出的数据。
