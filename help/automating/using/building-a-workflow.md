---
title: 构建工作流
description: 本节详细介绍创建新工作流的主要原则和最佳实践。
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
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# 构建工作流{#building-a-workflow}

本节详细介绍创建新工作流的主要原则和最佳实践。

## 工作流操作原则{#workflow-operating-principles}

工作流是一 **系列可配置活动**。 每个活动在该过程中都具有特定的角色。 每个活动的结果由一个过渡转发给下 **面的**&#x200B;活动，由箭头表示。

在一个活动与另一个活动之间交换的数据类型可能会影响以下的配置方式。 例如，如果在电子邮件投放活动之前建立了用户群，则它可以作为相关电子邮件的目标。

您可以打开活动，在执行工作流之前或之后检查或编辑参数。

您可以打开过渡，检查在执行工作流期间或执行工作流之后发送的数据是否正确。 要访问过渡的详细视图，您必须检查工作 **[!UICONTROL Keep interim results]** 流属性 **[!UICONTROL Execution]** 部分中的选项。

![](assets/workflow_overview.png)


## 创建工作流 {#creating-a-workflow}

您可以从项目、活动或营销活动列表创建工作流。

创建营销活动在创建营销 [活动部分有详细](../../start/using/marketing-activities.md#creating-a-marketing-activity) 。

1. 开始创建工作流类型营销活动后，请选择要使用的模板。

   ![](assets/workflow_creation_1.png)

   >[!NOTE]
   >
   >默认情况下，每个营销活动优惠多种类型。 这些参数允许您根据需要预配置某些参数。 有关详细信息，请参阅管 [理模板](../../start/using/marketing-activity-templates.md) 部分。

1. 输入工作流的常规属性。

   ![](assets/workflow_creation_2.png)

   您可以在“标签”字段中 **输入** 名称并修改ID。 活动名称及其ID显示在接口中，但消息收件人不可见。

   >[!NOTE]
   >
   >您可以从营销活动的列表在父活动中创建工作流。 您可以通过选择已创建的工作流来将此工作流链接到活动。

   您可以添加用户可在活动内容中看到的描述。

   由于如果工作流没有按照预期的方式执行，Adobe建议给他们正确的名称和标签，这样他们便更容易找到并排除故障： 填写工作流的描述字段，汇总要执行的过程，以便操作员能够轻松理解它。

1. 确认创建活动，随后将显示该活动的仪表板。 有关此方面的详细信息，请参 [阅工作流界面](../../automating/using/workflow-interface.md) 部分。

1. 准备好配置工作流后，您可以单击按钮以访问其他 **[!UICONTROL Edit properties]** 选项。 例如，您可以定义一个特定时区，默认情况下在工作流的所有活动中使用。 默认情况下，工作流的时区是为当前活动运算符定义的时区。

   ![](assets/workflow_properties.png)

**相关主题：**

* [创建工作流](https://docs.adobe.com/content/help/en/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html) 视频
* [工作流属性](../../automating/using/executing-a-workflow.md#workflow-properties)

## 添加和链接活动 {#adding-and-linking-activities}

您现在必须定义各种活动，并在图中将它们链接在一起。

>[!NOTE]
>
>如果未显示调色板，请单击工具栏的第一个按钮以显示它。

活动按类别在调色板的不同部分中进行分组。

* 第一部分包含定 [位活动](../../automating/using/about-targeting-activities.md)
* 第二部分包含执 [行活动](../../automating/using/about-execution-activities.md)，主要用于协调其他活动。
* 第三部分包含活动，可用于在不同渠道上发送 [消息](../../automating/using/about-channel-activities.md)。 此部分中的活动可能因实例中启用的渠道而异。
* 第四部分包含文 [件操作和数据管理活动](../../automating/using/about-data-management-activities.md)。

要创建图，请执行以下操作：

1. 从调色板中拖动活动并将其放入图中，即可添加该数据。

   例如，在图上添 **[加开始](../../automating/using/start-and-end.md)**，然后添**[&#x200B;加电子邮件](../../automating/using/email-delivery.md)** 投放活动。

1. 通过拖动活动开始 **活动** 过渡并将其放入电子邮件 **投放活动，将其链接到一起** 。

   >[!NOTE]
   >
   >通过将新活动放在上一个活动的结尾，您可以自动将链接到上一个过渡。

1. 添加所需活动并将它们链接在一起，以完成工作流程。

   >[!NOTE]
   >
   >您还可以通过复制粘贴现有活动来重复它们。 这样，您就可以保留最初定义的设置。 有关此内容的详细信息，请参 [阅复制工作流活动](../../automating/using/workflow-interface.md#duplicating-workflow-activities)。

将工作流活动关联在一起后，您便可以使用所选的标签对它们之 **间的过渡** 进行个性化。 为此，请多次单击过渡以访问其属性。

此外， **[!UICONTROL Targeting]** 活动 **[!UICONTROL Data management (ETL)]** 允许您为其出站 **过渡定** 义段代码。 然后，您可以根据这些段代码创建报告，以衡量营销活动的效率。 如需详细信息，请参阅[此部分](../../reporting/using/creating-a-report-workflow-segment.md)。

**工作流使用案例：**

* [用例： 创建每周一次的电子邮件投放](../../automating/using/workflow-weekly-offer.md)
* [用例： 在位置创建投放分段](../../automating/using/workflow-segmentation-location.md)
* [用例： 使用补充创建投放](../../automating/using/workflow-created-query-with-complement.md)
* [用例： 重定向工作流向非打开者发送新投放](../../automating/using/workflow-cross-channel-retargeting.md)

## 配置活动 {#configuring-activities}

默认情况下，活动未设置，如果未配置数据，将无法正确处理数据。 每个活动都包含多个选项卡，用于管理特定配置和活动通用选项，如出站过渡、标签等。

1. 确保所有活动正确连接。 某些活动需要检测传入数据的结构或性质，以优惠正确的配置选项。
1. 多次-单击某个活动或选择它，然后单 **[!UICONTROL Edit]** 击上下文操作以打开其配置窗口。
1. 编辑活动的标签。
1. 定义处理数据所需的所有不同选项。 请参阅本文档中活动的特定部分，了解每个活动的可能选项。
1. 保存活动，并为工作流的每个活动重复这些操作。
1. 保存工作流。
