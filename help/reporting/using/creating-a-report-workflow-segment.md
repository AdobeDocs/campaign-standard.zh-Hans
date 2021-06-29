---
solution: Campaign Standard
product: campaign
title: 根据工作流区段创建报告
description: 了解如何根据报表中的工作流区段检查交付是否成功。
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: 报告
role: Leader
level: Intermediate
exl-id: 514bffa0-2413-4212-b1b9-e070031c462f
source-git-commit: c001aaba50bdce8d949acc6daf74f3c7738bd117
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 2%

---

# 根据工作流区段创建报告{#creating-a-report-workflow-segment}

>[!CAUTION]
> **[!UICONTROL Segment code]**只能定位电子邮件和短信投放。

在创建工作流并将群体过滤到不同的目标受众后，您可以根据此定位工作流中定义的区段来衡量营销活动的效率。
要在报表中定位这些区段，请执行以下操作：

* [步骤1:使用区段更新用户档案自定义资源](#step-1--update-profiles-custom-resource-segments)
* [步骤2:使用区段创建工作流](#step-2--create-a-workflow-segments)
* [步骤3:创建动态报告以过滤区段](#step-3--create-a-dynamic-report-filter-segments)

>[!CAUTION]
>必须接受动态报告使用协议才能开始收集这些数据。
>
>有关本协议的更多信息，请参阅此[页面](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

## 步骤1:使用区段更新用户档案自定义资源{#step-1--update-profiles-custom-resource-segments}

在报告区段代码之前，您需要更新&#x200B;**[!UICONTROL Profiles]**&#x200B;自定义资源，以便存储区段代码。

1. 从高级菜单中，通过Adobe Campaign徽标，选择&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]**，然后选择&#x200B;**[!UICONTROL Profile (profile)]**&#x200B;资源。
1. 在&#x200B;**[!UICONTROL Data structure]**&#x200B;选项卡的&#x200B;**[!UICONTROL Sending logs extension]**&#x200B;菜单中，选中&#x200B;**[!UICONTROL Add segment code]**&#x200B;以允许存储定向工作流中的区段代码，并将其发送到动态报告。

   然后，**[!UICONTROL Segment code]**&#x200B;将在报表的&#x200B;**[!UICONTROL Profile]**&#x200B;维度部分中可用。

   ![](assets/report_segment_4.png)

1. 保存自定义资源。

1. 您现在需要发布自定义资源。
从高级菜单中，选择**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publishing]**。

   ![](assets/custom_profile_7.png)

1. 单击&#x200B;**[!UICONTROL Prepare publication]**，准备完成后，单击&#x200B;**[!UICONTROL Publish]**&#x200B;按钮。 有关自定义资源的详细信息，请参阅此[页面](../../developing/using/updating-the-database-structure.md)。

您现在可以使用区段代码开始创建工作流。

请注意，一旦在&#x200B;**[!UICONTROL Sending logs extension]**&#x200B;中启用段码，将立即收集段码。

## 步骤2:使用区段创建工作流 {#step-2--create-a-workflow-segments}

>[!NOTE]
>如果电子邮件投放的输入过渡为空，则默认情况下会添加上一个过渡的段码。

您首先需要创建具有不同目标群体的工作流。 在此，我们希望发送一封根据受众年龄进行个性化的电子邮件：一次交付20至30岁用户档案，另一次交付30至40岁用户档案。

1. 创建工作流。 有关如何创建工作流的更多详细信息，请参阅此[页面](../../automating/using/building-a-workflow.md)。

1. 将&#x200B;**[!UICONTROL Query]**&#x200B;活动从面板中拖放到工作区中，以添加该活动。

1. 将20到40岁的用户档案定位到以后，将其细分为更有针对性的人群。

   ![](assets/report_segment_1.png)

1. 添加&#x200B;**[!UICONTROL Segmentation]**&#x200B;活动，将查询结果拆分为两个目标群体。 有关分段的更多信息，请参阅此[页面](../../automating/using/segmentation.md)。

1. 双击&#x200B;**[!UICONTROL Segmentation]**&#x200B;活动以对其进行配置。 通过单击&#x200B;**[!UICONTROL Edit properties]**&#x200B;编辑第一个区段。

   ![](assets/report_segment_7.png)

1. 在20到30岁之间查询用户档案，完成后单击&#x200B;**[!UICONTROL Confirm]**。

   ![](assets/report_segment_8.png)

1. 单击&#x200B;**[!UICONTROL Add an element]**&#x200B;以创建第二个区段，并按照上述步骤中所述对其进行配置，以定位年龄在30到40岁之间的用户档案。

1. 编辑要通过动态报告传递的每个群体的&#x200B;**[!UICONTROL Segment code]**。

   >[!NOTE]
   >此步骤是强制性的，否则您将无法了解要报告哪些区段。

   ![](assets/report_segment_9.png)

1. 将&#x200B;**[!UICONTROL Email delivery]**&#x200B;活动拖放到区段之后。

   ![](assets/report_segment_3.png)

1. 根据不同的定向群体，将投放个性化。 有关创建电子邮件的更多信息，请参阅此[页面](../../designing/using/designing-content-in-adobe-campaign.md)。

1. 保存工作流。

1. 在工作流准备就绪后，单击&#x200B;**[!UICONTROL Start]**。

您现在可以访问报表以跟踪区段代码。

## 步骤3:创建动态报告以过滤区段 {#step-3--create-a-dynamic-report-filter-segments}

使用工作流发送投放后，您可以使用工作流中的区段代码划分报表。

1. 从&#x200B;**[!UICONTROL Reports]**&#x200B;选项卡中，选择现成报表或单击&#x200B;**[!UICONTROL Create new project]**&#x200B;按钮以从头开始创建报表。

   ![](assets/custom_profile_18.png)
1. 将&#x200B;**[!UICONTROL Delivery]**&#x200B;维度拖放到自由格式表中。

   ![](assets/report_segment_5.png)

1. 将不同的量度（如&#x200B;**[!UICONTROL Open]**&#x200B;和&#x200B;**[!UICONTROL Click]**&#x200B;量度）拖放到表中，以开始过滤数据。
1. 在&#x200B;**[!UICONTROL Dimensions]**&#x200B;类别中，单击&#x200B;**[!UICONTROL Profile]**&#x200B;维度，然后将&#x200B;**[!UICONTROL Segment code]**&#x200B;维度拖放到工作流的投放中，以根据目标群体衡量电子邮件投放是否成功。

   ![](assets/report_segment_6.png)

1. 根据需要，在工作区中拖放可视化图表。

   ![](assets/report_segment_10.png)
