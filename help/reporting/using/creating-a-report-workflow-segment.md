---
title: 根据工作流区段创建报告
description: 了解如何根据您的工作流在报表中的区段检查投放是否成功。
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: 514bffa0-2413-4212-b1b9-e070031c462f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 2%

---

# 根据工作流区段创建报告{#creating-a-report-workflow-segment}

>[!CAUTION]
> **[!UICONTROL Segment code]**&#x200B;只能定向电子邮件和短信投放。

在创建工作流并将群体筛选到不同的目标受众后，您可以根据此定位工作流中定义的区段衡量营销活动的效率。
要在报表中定位这些区段，请执行以下操作：

* [步骤1：使用区段更新用户档案自定义资源](#step-1--update-profiles-custom-resource-segments)
* [步骤2：创建包含区段的工作流](#step-2--create-a-workflow-segments)
* [第3步：创建动态报告以过滤区段](#step-3--create-a-dynamic-report-filter-segments)

>[!CAUTION]
>必须接受动态报告使用协议才能开始收集这些数据。
>
>有关此协议的详细信息，请参阅此[页面](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

## 步骤1：使用区段更新用户档案自定义资源{#step-1--update-profiles-custom-resource-segments}

在报告段代码之前，您需要更新&#x200B;**[!UICONTROL Profiles]**&#x200B;自定义资源以存储段代码。

1. 从高级菜单中，通过Adobe Campaign徽标，选择&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]**，然后选择&#x200B;**[!UICONTROL Profile (profile)]**&#x200B;资源。
1. 在&#x200B;**[!UICONTROL Data structure]**&#x200B;选项卡的&#x200B;**[!UICONTROL Sending logs extension]**&#x200B;菜单中，选中&#x200B;**[!UICONTROL Add segment code]**&#x200B;以允许从定位工作流中存储区段代码并将其发送到动态报告。

   然后，**[!UICONTROL Segment code]**&#x200B;将在报表的&#x200B;**[!UICONTROL Profile]**&#x200B;维度部分中可用。

   ![](assets/report_segment_4.png)

1. 保存您的自定义资源。

1. 您现在需要发布自定义资源。
从高级菜单中选择&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publishing]**。

   ![](assets/custom_profile_7.png)

1. 单击&#x200B;**[!UICONTROL Prepare publication]**，准备完成后，单击&#x200B;**[!UICONTROL Publish]**&#x200B;按钮。 有关自定义资源的详细信息，请参阅此[页](../../developing/using/updating-the-database-structure.md)。

您现在可以开始使用区段代码创建工作流了。

请注意，在&#x200B;**[!UICONTROL Sending logs extension]**&#x200B;中启用段代码后，将立即收集段代码。

## 步骤2：创建包含区段的工作流 {#step-2--create-a-workflow-segments}

>[!NOTE]
>如果电子邮件投放的输入过渡为空，则默认情况下将添加上一个过渡的段码。

您首先需要创建具有不同目标群体的工作流。 在本例中，我们希望发送一封电子邮件，该电子邮件将根据受众的年龄进行个性化：一次投放适用于20至30岁的用户档案，另一次投放适用于30至40岁的用户档案。

1. 创建工作流。 有关如何创建工作流的更多详细信息，请参阅此[页面](../../automating/using/building-a-workflow.md)。

1. 通过从面板中拖动一个&#x200B;**[!UICONTROL Query]**&#x200B;活动并将其放到工作区中来添加该活动。

1. 定向20到40岁的用户档案，以便以后将其细分为更具针对性的群体。

   ![](assets/report_segment_1.png)

1. 添加&#x200B;**[!UICONTROL Segmentation]**&#x200B;活动以将查询结果拆分为两个定向群体。 有关分段的更多信息，请参阅此[页面](../../automating/using/segmentation.md)。

1. 双击&#x200B;**[!UICONTROL Segmentation]**&#x200B;活动以对其进行配置。 通过单击&#x200B;**[!UICONTROL Edit properties]**&#x200B;编辑第一个区段。

   ![](assets/report_segment_7.png)

1. 查询年龄在20到30岁之间的用户档案，完成后，单击&#x200B;**[!UICONTROL Confirm]**。

   ![](assets/report_segment_8.png)

1. 单击&#x200B;**[!UICONTROL Add an element]**&#x200B;以创建您的第二个区段，并按照上述步骤将其配置为定向年龄在30到40岁之间的用户档案。

1. 编辑每个通过动态报告传递的群体的&#x200B;**[!UICONTROL Segment code]**。

   >[!NOTE]
   >此步骤为必填项，否则您将无法了解要报告的区段。

   ![](assets/report_segment_9.png)

1. 将&#x200B;**[!UICONTROL Email delivery]**&#x200B;活动拖放到区段之后。

   ![](assets/report_segment_3.png)

1. 根据不同的定向群体，对投放进行个性化设置。 有关电子邮件创建的更多信息，请参阅此[页面](../../designing/using/designing-content-in-adobe-campaign.md)。

1. 保存工作流。

1. 工作流准备就绪后，单击&#x200B;**[!UICONTROL Start]**。

您现在可以访问报表来跟踪区段代码。

## 第3步：创建动态报告以过滤区段 {#step-3--create-a-dynamic-report-filter-segments}

使用工作流发送投放后，您可以使用工作流中的区段代码来划分报表。

1. 从&#x200B;**[!UICONTROL Reports]**&#x200B;选项卡中，选择一个现成的报表或单击&#x200B;**[!UICONTROL Create new project]**&#x200B;按钮以从头开始创建报表。

   ![](assets/custom_profile_18.png)
1. 将&#x200B;**[!UICONTROL Delivery]**&#x200B;维度拖放到自由格式表中。

   ![](assets/report_segment_5.png)

1. 将不同的量度（如&#x200B;**[!UICONTROL Open]**&#x200B;和&#x200B;**[!UICONTROL Click]**&#x200B;量度）拖放到表中以开始筛选数据。
1. 在&#x200B;**[!UICONTROL Dimensions]**&#x200B;类别中，单击&#x200B;**[!UICONTROL Profile]**&#x200B;维度，然后将&#x200B;**[!UICONTROL Segment code]**&#x200B;维度拖放到工作流的投放中，以根据定向群体衡量电子邮件投放是否成功。

   ![](assets/report_segment_6.png)

1. 如果需要，可将可视化图表拖放到工作区中。

   ![](assets/report_segment_10.png)
