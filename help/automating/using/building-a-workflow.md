---
title: 构建工作流
description: 本节详细介绍了创建新工作流的主要原则和最佳做法。
page-status-flag: never-activated
uuid: 11374f64-8d34-40da-937b-09f419250f4c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: c26fcb0e-19d5-4bd5-b7d6-2d22ce92ad90
context-tags: workflow,wizard;workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 41ba6fa44807541dd749f4effca44ae2b4d147ae

---


# 构建工作流{#building-a-workflow}

本节详细介绍了创建新工作流的主要原则和最佳实践：

* 创建工作流。
* 添加和链接活动。
* 配置活动。

## 创建工作流 {#creating-a-workflow}

您可以从计划、营销活动或营销活动列表创建工作流。

有关创建营销活动的详细信息，请参 [阅创建营销活动](../../start/using/marketing-activities.md#creating-a-marketing-activity) 。

1. 开始创建工作流类型营销活动后，请选择要使用的模板。

   ![](assets/workflow_creation_1.png)

   >[!NOTE]
   >
   >默认情况下，每个营销活动提供多种类型。 这些参数允许您根据需要预配置某些参数。 有关详细信息，请参阅管理模 [板一节](../../start/using/marketing-activity-templates.md) 。

1. 输入工作流的常规属性。

   ![](assets/workflow_creation_2.png)

   您可以在“标签”字段中输入 **名称** ，然后修改ID。 活动名称及其ID显示在界面中，但邮件收件人看不到这些名称和ID。

   >[!NOTE]
   >
   >您可以从营销活动列表中在父营销活动中创建工作流。 您可以通过选择已创建的营销活动来将此工作流关联到营销活动。

   您可以添加用户可在营销活动内容中看到的描述。

   由于如果它们没有以预期的方式执行，可以更轻松地查找和排除故障，Adobe建议为工作流提供正确的名称和标签：填写工作流的描述字段以汇总要执行的过程，以便操作员能够轻松理解它。

1. 确认创建活动，随后将显示该活动的功能板。 有关详细信息，请参阅“工作 [流界面](../../automating/using/workflow-interface.md) ”部分。

1. 准备好配置工作流后，您可以单击按钮以访问其他选 **[!UICONTROL Edit properties]**项。 例如，您可以定义一个特定时区，默认情况下在工作流的所有活动中使用。 默认情况下，工作流的时区是为当前营销活动操作员定义的时区。

   ![](assets/workflow_properties.png)

**相关主题：**

[创建工作流视频](https://docs.adobe.com/content/help/en/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html)

## 添加和链接活动 {#adding-and-linking-activities}

您现在必须定义各种活动，并在图中将它们链接在一起。

>[!NOTE]
>
>如果未显示调板，请单击工具栏的第一个按钮以显示它。

活动按类别分组在调色板的不同部分中。

* 第一部分包含定位活动。
* 第二节包括执行活动，主要用于协调其他活动。
* 第三部分包含可用于在不同渠道上发送消息的活动。 此部分中的活动可能因实例上启用的渠道而异。
* 第四部分包含文件处理和数据管理活动。

要创建图，请执行以下操作：

1. 通过从调色板中拖动活动并将其放入图中来添加活动。

   例如，在图中添 **加开始** ，然后添 **加电子邮件交付** 。

1. 将“开始”活动过渡拖放到“电 **子邮件** ”交付活动中，将活动链 **接到一起** 。

   >[!NOTE]
   >
   >通过在上一个活动的过渡结束时放置新活动，可以自动将活动链接到上一个活动。

1. 添加所需的活动并将它们链接在一起，以完成您的工作流。

   >[!NOTE]
   >
   >您还可以通过复制粘贴来复制现有活动。 这样，您就可以保留最初定义的设置。 有关此内容的详细信息，请参阅复 [制工作流活动](../../automating/using/workflow-interface.md#duplicating-workflow-activities)。

将工作流活动关联在一起后，您便可以使用您选择的标签个性化它们 **之间的** 过渡。 为此，请双击过渡以访问其属性。

此外，活 **[!UICONTROL Targeting]**动**[!UICONTROL Data management (ETL)]** 允许您为其出站过 **渡定义段代码** 。 然后，您可以根据这些细分代码创建报告，以衡量营销活动的效率。 如需详细信息，请参阅[此部分](../../reporting/using/creating-a-report-workflow-segment.md)。

**工作流使用案例：**

* [用例：创建每周一次的电子邮件发送](../../automating/using/workflow-weekly-offer.md)
* [用例：创建按位置分段的交付](../../automating/using/workflow-segmentation-location.md)
* [用例：使用补充创建交付](../../automating/using/workflow-created-query-with-complement.md)
* [用例：重定向工作流向非打开者发送新分发](../../automating/using/workflow-cross-channel-retargeting.md)

## 配置活动 {#configuring-activities}

默认情况下，活动未设置，如果未配置，则无法正确处理数据。 每个活动都包含多个选项卡，用于管理特定配置和活动通用选项，如出站过渡、标签等。

1. 确保所有活动都正确连接。 某些活动需要检测传入数据的结构或性质以提供正确的配置选项。
1. 双击某个活动或选择该活动，然后单击上下文 **[!UICONTROL Edit]**操作以打开其配置窗口。
1. 编辑活动的标签。
1. 定义处理数据所需的所有不同选项。 请参阅本文档中活动的特定部分，了解每个活动的可能选项。
1. 保存活动，并为工作流的每个活动重复这些操作。
1. 保存工作流。
