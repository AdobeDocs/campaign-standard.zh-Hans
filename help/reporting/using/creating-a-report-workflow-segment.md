---
solution: Campaign Standard
product: campaign
title: 根据工作流区段创建报告
description: 了解如何根据投放在报告中的细分情况检查工作流的成功与否。
audience: reporting
content-type: reference
topic-tags: customizing-reports
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 2%

---


# 根据工作流区段创建报告{#creating-a-report-workflow-segment}

在创建工作流并将人口筛选为不同的目标受众后，您可以根据此定位工作流中定义的细分来衡量营销活动的效率。
要在报表中目标这些区段，请执行以下操作：

* [第1步：使用区段更新用户档案自定义资源](#step-1--update-profiles-custom-resource-segments)
* [第2步：创建包含区段的工作流](#step-2--create-a-workflow-segments)
* [第3步：创建动态报表以筛选区段](#step-3--create-a-dynamic-report-filter-segments)

>[!CAUTION]
>必须接受动态报告使用协议，以便开始收集这些数据。
>For more on this agreement, refer to this [page](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## 第1步：使用区段更新用户档案自定义资源{#step-1--update-profiles-custom-resource-segments}

在报告段代码之前，您需要更新自 **[!UICONTROL Profiles]** 定义资源以便存储段代码。

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]**, then select the **[!UICONTROL Profile (profile)]** resource.
1. 在选 **[!UICONTROL Sending logs extension]** 项卡的菜 **[!UICONTROL Data structure]** 单中，选 **[!UICONTROL Add segment code]** 中以允许段代码定位工作流并将其发送到动态报告。

   随 **[!UICONTROL Segment code]** 后，报表的维 **[!UICONTROL Profile]** 度部分中将提供该选项。

   ![](assets/report_segment_4.png)

1. 保存您的自定义资源。

1. 您现在需要发布自定义资源。
从高级菜单中，选择 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publishing]**。

   ![](assets/custom_profile_7.png)

1. 单 **[!UICONTROL Prepare publication]** 击，准备完成后，单击按 **[!UICONTROL Publish]** 钮。 For more information on custom resource, refer to this [page](../../developing/using/updating-the-database-structure.md).

您现在可以开始使用段代码创建工作流。

请注意，一旦在中启用段代码，将立即收集该段代码 **[!UICONTROL Sending logs extension]**。

## 第2步：创建包含区段的工作流 {#step-2--create-a-workflow-segments}

>[!NOTE]
>如果电子邮件过渡的输入投放为空，则默认情况下将添加上一个过渡的段代码。

您首先需要创建具有不同目标群体的工作流。 在此，我们希望发送一封根据受众年龄个性化的电子邮件：一个投放为20至30岁的用户档案，另一个为30至40岁的用户档案。

1. 创建您的工作流。 For more details on how to create your workflow, refer to this [page](../../automating/using/building-a-workflow.md).

1. Add a **[!UICONTROL Query]** activity by dragging it from the palette and dropping it in the workspace.

1. 目标用户档案年龄在20到40岁之间，后来将他们细分为更有针对性的人群。

   ![](assets/report_segment_1.png)

1. 添加活动 **[!UICONTROL Segmentation]** 以将查询结果拆分为两个目标人群。 For more on segmentation, refer to this [page](../../automating/using/segmentation.md).

1. 多次单击 **[!UICONTROL Segmentation]** 活动进行配置。 通过单击编辑第一个区段 **[!UICONTROL Edit properties]**。

   ![](assets/report_segment_7.png)

1. 查询用户档案在20到30岁之间，完成后单击 **[!UICONTROL Confirm]** 鼠标。

   ![](assets/report_segment_8.png)

1. 单 **[!UICONTROL Add an element]** 击以创建第二个区段，并按照以上步骤中的说明进行配置，以在30到40岁之间目标用户档案。

1. 编辑 **[!UICONTROL Segment code]** 要通过动态报告传递的每个人口。

   >[!NOTE]
   >此步骤是强制性的，否则您将无法了解要报告的区段。

   ![](assets/report_segment_9.png)

1. Drag and drop an **[!UICONTROL Email delivery]** activity after your segments.

   ![](assets/report_segment_3.png)

1. 根据不同的目标人群，个性化您的投放。 For more on email creation, refer to this [page](../../designing/using/designing-content-in-adobe-campaign.md).

1. 保存工作流。

1. 在工 **[!UICONTROL Start]** 作流准备就绪时单击。

您现在可以访问报告来跟踪段代码。

## 第3步：创建动态报表以筛选区段 {#step-3--create-a-dynamic-report-filter-segments}

在使用工作流发送投放后，您可以使用工作流中的段代码细分报表。

1. 在选 **[!UICONTROL Reports]** 项卡中，选择现成报告，或单击按钮从头 **[!UICONTROL Create new project]** 开始开始一个报告。

   ![](assets/custom_profile_18.png)
1. 将维拖放 **[!UICONTROL Delivery]** 到自由形式表中。

   ![](assets/report_segment_5.png)

1. 将不同的度量拖放到表中，如和度 **[!UICONTROL Open]** 量 **[!UICONTROL Click]** 以开始筛选数据。
1. 在类别 **[!UICONTROL Dimensions]** 中，单击维 **[!UICONTROL Profile]** 度，然后将维度拖放到工作 **[!UICONTROL Segment code]** 流的投放上，以根据目标人群来衡量电子邮件投放的成功程度。

   ![](assets/report_segment_6.png)

1. 根据需要在工作区中拖放一个可视化内容。

   ![](assets/report_segment_10.png)
