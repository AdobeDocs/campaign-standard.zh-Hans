---
title: 构建工作流
description: 本节详细介绍创建新工作流的主要原理和最佳实践。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,wizard;workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 7553588c-4679-4dfd-93cb-e705ad4dc0aa
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '976'
ht-degree: 90%

---

# 构建工作流{#building-a-workflow}

本节详细介绍创建新工作流的主要原理和最佳实践。

## 工作流的工作原理{#workflow-operating-principles}

工作流是&#x200B;**一系列可配置的活动**。在该过程中，每个活动都具有特定的角色。每个活动的结果通过&#x200B;**过渡**&#x200B;活动转发到下一个活动，由箭头表示。

在一个活动与另一个活动之间交换的数据类型，可能会影响后续活动的配置方式。例如，如果在电子邮件投放活动之前建立了群体，则该群体可以用作相关电子邮件的目标。

在执行工作流之前或之后，您可以打开活动，检查或编辑参数。

您可以打开过渡，检查在执行工作流期间或执行工作流之后发送的数据是否正确。要访问过渡的详细视图，您必须勾选工作流属性 **[!UICONTROL Keep interim results]** 部分中的 **[!UICONTROL Execution]** 选项。

>[!CAUTION]
>
>使用此选项会占用大量磁盘空间，其目的在于帮助您构建工作流并确保配置和行为正确。在制作实例中，请不要勾选该选项。

![](assets/workflow_overview.png)

## 创建工作流 {#creating-a-workflow}

您可以从项目、营销策划或营销活动列表创建工作流。

![](assets/do-not-localize/how-to-video.png) [了解如何在视频中构建工作流](#video)

有关创建营销活动的详情，请参阅[创建营销活动](../../start/using/marketing-activities.md#creating-a-marketing-activity)一节。

1. 开始创建工作流类型营销活动后，即可选择要使用的模板。

   ![](assets/workflow_creation_1.png)

   >[!NOTE]
   >
   >默认情况下，每个营销活动会提供多种类型。利用这些类型，可根据需要预配置某些参数。有关更多信息，请参阅[管理模板](../../start/using/marketing-activity-templates.md)一节。

1. 输入工作流的常规属性。

   ![](assets/workflow_creation_2.png)

   您可以在 **Label** 字段中输入名称并修改 ID。界面中会显示活动名称及其 ID，但消息收件人看不到它们。

   >[!NOTE]
   >
   >您可以使用营销活动列表，在父营销策划中创建工作流。您可以通过选择已创建的工作流，将此工作流链接到营销策划。

   您可以添加用户会在营销策划内容中看到的描述。

   Adobe 建议为工作流赋予正确的名称和标签，这样工作流没有按照预期的方式执行，可轻松地找到并排除故障：填写工作流的描述字段，在其中加入执行流程的摘要，以便操作员能够轻松理解。

1. 确认创建活动，随后将显示该活动的仪表板。有关更多信息，请参阅[工作流界面](../../automating/using/workflow-interface.md)一节。

1. 准备好配置工作流后，您可以通过单击&#x200B;**[!UICONTROL Edit properties]**&#x200B;按钮访问其他选项。

   例如，您可以定义一个默认用于工作流所有活动的特定时区。默认情况下，工作流的时区就是为当前 Campaign 操作人员定义的时区。

   有关工作流属性的详细信息，请参阅[此页面](../../automating/using/managing-execution-options.md)。

   ![](assets/workflow_properties.png)

## 添加和链接活动 {#adding-and-linking-activities}

您现在必须定义各种活动，并在图表中将它们链接到一起。

>[!NOTE]
>
>如果未显示面板，请单击工具栏的第一个按钮以显示面板。

各个活动按照类别分组到了面板内部的不同部分。

* 第一部分包含[定向活动](../../automating/using/about-targeting-activities.md)
* 第二部分包含[执行活动](../../automating/using/about-execution-activities.md)，主要用于协调其他活动。
* 第三部分包含可用于在不同[渠道](../../automating/using/about-channel-activities.md)上发送消息的活动。此部分中的活动可能因实例中启用的渠道而异。
* 第四部分包含[文件操作和数据管理活动](../../automating/using/about-data-management-activities.md)。

要创建图表，请执行以下操作：

1. 将某个活动从面板中拖放到图表中，以添加该活动。

   例如，在图表上添加&#x200B;**[开始](../../automating/using/start-and-end.md)**&#x200B;活动，然后添加&#x200B;**[电子邮件投放](../../automating/using/email-delivery.md)**&#x200B;活动。

1. 通过将&#x200B;**开始**&#x200B;活动过渡拖放到&#x200B;**电子邮件投放**&#x200B;活动上，将两个活动链接到一起。

   >[!NOTE]
   >
   >通过将新活动放在上一个活动的末尾，您可以自动将新活动与上一个活动链接到一起。

1. 添加所需活动并将它们链接在一起，以完成工作流程。

   >[!NOTE]
   >
   >您还可以通过复制粘贴操作以复制现有活动。这样，您就可以保留最初定义的设置。有关更多信息，请参见[复制工作流活动](../../automating/using/workflow-interface.md#duplicating-workflow-activities)。

将工作流活动链接到一起后，您即可使用所选的&#x200B;**标签**&#x200B;对它们之间的过渡进行个性化。要实现此操作，请双击过渡以访问其属性。

此外，利用 **[!UICONTROL Targeting]** 和 **[!UICONTROL Data management (ETL)]** 活动，可为叫客过渡定义&#x200B;**区段代码**。然后，您可以根据这些区段代码创建报告，以衡量营销活动的效果。有关更多信息，请参阅[此章节](../../reporting/using/creating-a-report-workflow-segment.md)。

**工作流使用案例：**

* [用例：创建每周一次的电子邮件投放](../../automating/using/workflow-weekly-offer.md)
* [使用案例：创建基于位置划分的投放](../../automating/using/workflow-segmentation-location.md)
* [使用案例：创建带补码的投放](../../automating/using/workflow-created-query-with-complement.md)
* [使用案例：重定向工作流 — 向未打开者发送新投放](../../automating/using/workflow-cross-channel-retargeting.md)

## 配置活动 {#configuring-activities}

默认情况下，如果不配置活动，就代表未正确设置活动，也无法正确处理数据。每个活动都包含多个选项卡，用于管理特定配置和活动通用选项，如叫客过渡、标签等。

1. 确保所有活动正确连接。部分活动需要检测传入数据的结构或性质，以提供正确的配置选项。
1. 双击某个活动，或将其选中然后单击 **[!UICONTROL Edit]** 上下文操作以打开其配置窗口。
1. 编辑活动的标签。
1. 定义处理数据所需的所有不同选项。请参阅本文档中关于活动的特定章节，了解每个活动可使用的选项。
1. 保存活动，并为工作流的每个活动重复这些操作。
1. 保存工作流。

## 教程视频 {#video}

本视频说明如何创建工作流。

>[!VIDEO](https://video.tv.adobe.com/v/23937?quality=12)

[此处](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=zh-Hans)提供了其他Campaign Standard操作方法视频。
