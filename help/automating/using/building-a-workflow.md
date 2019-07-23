---
title: 构建工作流
seo-title: 构建工作流
description: 构建工作流
seo-description: 本节详细介绍了创建新工作流程的主要原则和最佳做法。
page-status-flag: 从未激活
uuid: 11374f648-40da-937b-09f419250f4c
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 工作流常规操作
discoiquuid: c26fcb0e-19d5-4bd5-b7 d6-2d22 ce92 ad90
context-tags: 工作流程，向导；工作流，主要
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 51154892b2d5bd5685272735cdd6e7d9474e09a6

---


# Building a workflow{#building-a-workflow}

本节详细介绍了创建新工作流程的主要原则和最佳做法：

* 创建工作流。
* 添加和链接活动。
* 配置活动。

## Creating a workflow {#creating-a-workflow}

您可以从计划、营销活动或营销活动列表创建工作流。

Creating a marketing activity is detailed in the [Creating marketing activities](../../start/using/marketing-activities.md#creating-a-marketing-activity) section.

1. 开始创建工作流类型营销活动后，请选择要使用的模板。

   ![](assets/workflow_creation_1.png)

   >[!NOTE]
   >
   >默认情况下，每个营销活动提供几种类型。这些组件允许您根据需要预配置某些参数。For more information, refer to the [Managing templates](../../start/using/about-templates.md) section.

1. 输入工作流的常规属性。

   ![](assets/workflow_creation_2.png)

   You can enter a name in the **Label** field and modify the ID. 活动名称及其ID显示在界面中，但消息收件人不可见。

   >[!NOTE]
   >
   >您可以从营销活动列表中创建父营销活动中的工作流。您可以通过选择已经创建的营销活动将此工作流链接到营销活动。

   您可以添加用户可在营销活动内容中看到的描述。

   由于其使他们能够更轻松地查找并排除在预期的方式下执行的操作，因此Adobe建议您提供工作流的适当名称和标签：填写工作流的描述字段以总结要执行的进程，以便操作员能够轻松理解。

1. 确认创建活动，随后将显示该活动的仪表板。For more on this, refer to the [Workflow interface](../../automating/using/workflow-interface.md) section.

**相关主题：**

[创建工作流](https://helpx.adobe.com/campaign/kt/acs/using/acs-create-workflow-feature-video-use.html) 视频

## Adding and linking activities {#adding-and-linking-activities}

您现在必须定义各种活动，并将它们链接到图表中。

>[!NOTE]
>
>如果未显示调色板，请单击工具栏的第一个按钮以显示它。

活动按类别的不同部分内的类别分组。

* 第一部分包含定位活动。
* 第二部分包含执行活动，主要用于协调其他活动。
* 第三部分包含可用于在不同渠道发送消息的活动。此部分中的活动可能因实例上启用的渠道而异。
* 第四部分包含文件处理和数据管理活动。

要创建图表，请执行以下操作：

1. 通过将活动从调色板拖动到图表中，添加活动。

   For example, add a **Start** activity and then an **Email delivery** activity on the diagram.

1. Link the activities together by dragging the **Start** activity transition and dropping it on to the **Email delivery** activity.

   >[!NOTE]
   >
   >您可以在之前的过渡结束时放置新活动，从而自动将活动链接到上一个活动。

1. 添加所需的活动，并将它们链接到一起以完成工作流程。

   >[!NOTE]
   >
   >您还可以通过复制现有活动复制现有活动。这样，您就可以保留最初定义的设置。For more on this, refer to [Duplicating workflow activities](../../automating/using/workflow-interface.md#duplicating-workflow-activities).

Once your workflow activities are linked together, you can personalize the transitions between them with the **label** of your choice. 要执行此操作，请双击过渡以访问其属性。

**[!UICONTROL Targeting]****[!UICONTROL Data management (ETL)]** 此外，活动允许您为出站过渡定义 **细分代码** 。然后，您可以根据这些区段代码创建报告，以衡量营销活动的效率。For more on this, refer to [this section](../../reporting/using/creating-a-report-workflow-segment.md).

## Configuring activities {#configuring-activities}

默认情况下，活动未设置，如果未配置数据，则无法正确处理数据。每个活动都包含多个用于管理特定配置和活动的选项卡，如出站过渡、标签等。

1. 确保所有活动都已正确连接。某些活动需要检测传入数据的结构或性质以提供正确的配置选项。
1. Double-click an activity or select it and click the **[!UICONTROL Edit]** contextual action to open its configuration window.
1. 编辑活动的标签。
1. 定义处理数据所需的所有不同选项。请参阅本文档的活动特定部分，了解每个活动的可能选项。
1. 保存活动，并为工作流的每个活动重复这些操作。
1. 保存工作流。

