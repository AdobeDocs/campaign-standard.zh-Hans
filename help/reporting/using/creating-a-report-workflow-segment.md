---
title: 根据工作流区段创建报告
description: 了解如何根据报表中的工作流区段检查投放是否成功。
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: 514bffa0-2413-4212-b1b9-e070031c462f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 2%

---

# 根据工作流区段创建报告{#creating-a-report-workflow-segment}

>[!CAUTION]
> **[!UICONTROL Segment code]**只能定位电子邮件和短信投放。

在创建工作流并将群体筛选到不同的目标受众后，您可以根据此定位工作流中定义的区段衡量营销活动的效率。
要在报表中定位这些区段，请执行以下操作：

* [步骤1：使用区段更新用户档案自定义资源](#step-1--update-profiles-custom-resource-segments)
* [步骤2：创建包含区段的工作流](#step-2--create-a-workflow-segments)
* [步骤3：创建动态报告以过滤区段](#step-3--create-a-dynamic-report-filter-segments)

>[!CAUTION]
>必须接受动态报告使用情况协议才能开始收集这些数据。
>
>有关此协议的更多信息，请参阅此 [页面](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## 步骤1：使用区段更新用户档案自定义资源{#step-1--update-profiles-custom-resource-segments}

在报告区段代码之前，您需要更新 **[!UICONTROL Profiles]** 要存储的区段代码的自定义资源。

1. 从高级菜单中，通过Adobe Campaign徽标，选择 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]**，然后选择 **[!UICONTROL Profile (profile)]** 资源。
1. 在 **[!UICONTROL Sending logs extension]** 菜单 **[!UICONTROL Data structure]** 选项卡，选中 **[!UICONTROL Add segment code]** 允许从定位工作流中存储区段代码并将其发送到动态报告。

   此 **[!UICONTROL Segment code]** 随后将可用于 **[!UICONTROL Profile]** 报表的维度部分。

   ![](assets/report_segment_4.png)

1. 保存您的自定义资源。

1. 您现在需要发布自定义资源。
从高级菜单中，选择 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publishing]**.

   ![](assets/custom_profile_7.png)

1. 单击 **[!UICONTROL Prepare publication]** 然后，准备完成后，单击 **[!UICONTROL Publish]** 按钮。 有关自定义资源的详细信息，请参阅此 [页面](../../developing/using/updating-the-database-structure.md).

您现在可以使用区段代码开始创建工作流。

请注意，一旦您在中启用段代码，则将立即收集段代码。 **[!UICONTROL Sending logs extension]**.

## 步骤2：创建包含区段的工作流 {#step-2--create-a-workflow-segments}

>[!NOTE]
>如果电子邮件投放的输入过渡为空，则默认情况下将添加上一个过渡的区段代码。

您首先需要创建具有不同目标群体的工作流。 在本例中，我们希望发送一封电子邮件，该电子邮件将根据受众的年龄进行个性化：一次投放适用于20至30岁的用户档案，另一次投放适用于30至40岁的用户档案。

1. 创建工作流。 有关如何创建工作流的更多详细信息，请参阅此 [页面](../../automating/using/building-a-workflow.md).

1. 添加 **[!UICONTROL Query]** 活动，方法是将其从面板中拖放到工作区中。

1. 将20到40岁及以上的用户档案定位为更具针对性的群体。

   ![](assets/report_segment_1.png)

1. 添加 **[!UICONTROL Segmentation]** 活动，将查询结果拆分为两个定向群体。 有关分段的更多信息，请参阅此 [页面](../../automating/using/segmentation.md).

1. 双击 **[!UICONTROL Segmentation]** 活动以进行配置。 通过单击可编辑第一个区段 **[!UICONTROL Edit properties]**.

   ![](assets/report_segment_7.png)

1. 查询年龄在20到30岁之间的用户档案，然后单击 **[!UICONTROL Confirm]** 完成时。

   ![](assets/report_segment_8.png)

1. 单击 **[!UICONTROL Add an element]** 创建第二个区段，并按照上述步骤所述对其进行配置，以定向30至40岁的用户档案。

1. 编辑 **[!UICONTROL Segment code]** 每个群体均可通过动态报告进行传递。

   >[!NOTE]
   >此步骤为必填项，否则您将无法了解要报告的区段。

   ![](assets/report_segment_9.png)

1. 拖放 **[!UICONTROL Email delivery]** 区段后的活动。

   ![](assets/report_segment_3.png)

1. 根据不同的定向群体，对投放进行个性化设置。 有关电子邮件创建的更多信息，请参阅此 [页面](../../designing/using/designing-content-in-adobe-campaign.md).

1. 保存工作流。

1. 单击 **[!UICONTROL Start]** 工作流就绪时。

您现在可以访问报表来跟踪区段代码。

## 步骤3：创建动态报告以过滤区段 {#step-3--create-a-dynamic-report-filter-segments}

使用工作流发送投放后，您可以使用工作流中的区段代码划分报表。

1. 从 **[!UICONTROL Reports]** 选项卡，选择现成的报告或单击 **[!UICONTROL Create new project]** 按钮以从头开始创建。

   ![](assets/custom_profile_18.png)
1. 拖放 **[!UICONTROL Delivery]** 自由格式表的维度。

   ![](assets/report_segment_5.png)

1. 将不同的量度拖放到表中，例如 **[!UICONTROL Open]** 和 **[!UICONTROL Click]** 用于开始筛选数据的指标。
1. 在 **[!UICONTROL Dimensions]** 类别下，单击 **[!UICONTROL Profile]** 维度，然后拖放 **[!UICONTROL Segment code]** 工作流投放中的维度，用于根据定向群体衡量电子邮件投放是否成功。

   ![](assets/report_segment_6.png)

1. 如果需要，可将可视化图表拖放到工作区中。

   ![](assets/report_segment_10.png)
