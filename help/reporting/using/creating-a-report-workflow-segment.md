---
solution: Campaign Standard
product: campaign
title: 根据工作流区段创建报告
description: 了解如何根据报表中的投放细分来检查工作流是否成功。
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: Reporting
role: Leader
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '620'
ht-degree: 2%

---


# 根据工作流区段创建报告{#creating-a-report-workflow-segment}

在创建工作流并将人口筛选为不同的目标受众后，您可以根据在此定位工作流中定义的细分来衡量营销活动的效率。
要在报表中目标这些区段，请执行以下操作：

* [第1步：使用区段更新用户档案自定义资源](#step-1--update-profiles-custom-resource-segments)
* [第2步：创建包含区段的工作流](#step-2--create-a-workflow-segments)
* [第3步：创建动态报表以筛选区段](#step-3--create-a-dynamic-report-filter-segments)

>[!CAUTION]
>必须接受动态报告使用协议，以便开始收集这些数据。
>有关本协议的详细信息，请参阅此[页](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

## 第1步：使用区段{#step-1--update-profiles-custom-resource-segments}更新用户档案自定义资源

在报告段代码之前，您需要更新&#x200B;**[!UICONTROL Profiles]**&#x200B;自定义资源，以便存储段代码。

1. 从高级菜单中，通过Adobe Campaign徽标选择&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** ，然后选择&#x200B;**[!UICONTROL Profile (profile)]**&#x200B;资源。
1. 在&#x200B;**[!UICONTROL Data structure]**&#x200B;选项卡的&#x200B;**[!UICONTROL Sending logs extension]**&#x200B;菜单中，选中&#x200B;**[!UICONTROL Add segment code]**&#x200B;以允许存储段代码与目标工作流的关系，并将其发送到动态报告。

   然后，**[!UICONTROL Segment code]**&#x200B;将在报表的&#x200B;**[!UICONTROL Profile]**&#x200B;维度部分中可用。

   ![](assets/report_segment_4.png)

1. 保存您的自定义资源。

1. 您现在需要发布自定义资源。
从高级菜单中，选择**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publishing]**。

   ![](assets/custom_profile_7.png)

1. 单击&#x200B;**[!UICONTROL Prepare publication]**，准备完毕后单击&#x200B;**[!UICONTROL Publish]**&#x200B;按钮。 有关自定义资源的详细信息，请参阅此[页面](../../developing/using/updating-the-database-structure.md)。

您现在可以开始使用段代码创建工作流。

请注意，一旦在&#x200B;**[!UICONTROL Sending logs extension]**&#x200B;中启用段代码，将立即收集段代码。

## 第2步：使用区段{#step-2--create-a-workflow-segments}创建工作流

>[!NOTE]
>如果电子邮件投放的输入过渡为空，则默认情况下将添加上一个过渡的段代码。

您首先需要创建具有不同目标群体的工作流。 在此，我们希望发送一封根据受众年龄个性化的电子邮件：一个是20至30岁用户档案的投放，另一个是30至40岁用户档案的。

1. 创建您的工作流。 有关如何创建工作流的详细信息，请参阅此[页面](../../automating/using/building-a-workflow.md)。

1. 将&#x200B;**[!UICONTROL Query]**&#x200B;活动从调色板中拖放到工作区中，即可添加。

1. 目标从20岁到40岁的用户档案，以后将其细分为更有针对性的人群。

   ![](assets/report_segment_1.png)

1. 添加&#x200B;**[!UICONTROL Segmentation]**&#x200B;活动，将查询结果拆分为两个目标群体。 有关分段的详细信息，请参阅此[页面](../../automating/using/segmentation.md)。

1. 多次单击&#x200B;**[!UICONTROL Segmentation]**&#x200B;活动进行配置。 单击&#x200B;**[!UICONTROL Edit properties]**&#x200B;编辑第一个区段。

   ![](assets/report_segment_7.png)

1. 查询用户档案介于20到30岁之间，完成后单击&#x200B;**[!UICONTROL Confirm]**。

   ![](assets/report_segment_8.png)

1. 单击&#x200B;**[!UICONTROL Add an element]**&#x200B;创建第二个区段，并按照上述步骤中的说明对其进行配置，以目标30到40岁之间的用户档案。

1. 编辑通过动态报告传递的每个人口的&#x200B;**[!UICONTROL Segment code]**。

   >[!NOTE]
   >此步骤是必须执行的，否则您将无法了解要报告的区段。

   ![](assets/report_segment_9.png)

1. 将&#x200B;**[!UICONTROL Email delivery]**&#x200B;活动拖放到区段之后。

   ![](assets/report_segment_3.png)

1. 根据不同的目标人群个性化您的投放。 有关创建电子邮件的详细信息，请参阅此[页面](../../designing/using/designing-content-in-adobe-campaign.md)。

1. 保存工作流。

1. 工作流准备就绪后，单击&#x200B;**[!UICONTROL Start]**。

您现在可以访问报告以跟踪段代码。

## 第3步：创建动态报表以筛选区段{#step-3--create-a-dynamic-report-filter-segments}

在使用工作流发送投放后，您可以使用工作流中的段代码划分报表。

1. 从&#x200B;**[!UICONTROL Reports]**&#x200B;选项卡中，选择现成报告，或单击&#x200B;**[!UICONTROL Create new project]**&#x200B;按钮从头开始开始一个。

   ![](assets/custom_profile_18.png)
1. 将&#x200B;**[!UICONTROL Delivery]**&#x200B;维度拖放到自由格式表中。

   ![](assets/report_segment_5.png)

1. 将不同的量度拖放到表中，如&#x200B;**[!UICONTROL Open]**&#x200B;和&#x200B;**[!UICONTROL Click]**&#x200B;量度，以开始筛选数据。
1. 在&#x200B;**[!UICONTROL Dimensions]**&#x200B;类别中，单击&#x200B;**[!UICONTROL Profile]**&#x200B;维度，然后拖放工作流投放上的&#x200B;**[!UICONTROL Segment code]**&#x200B;维度，以根据目标群体来衡量电子邮件投放的成功程度。

   ![](assets/report_segment_6.png)

1. 根据需要在工作区中拖放一个可视化。

   ![](assets/report_segment_10.png)
