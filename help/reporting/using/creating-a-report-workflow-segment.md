---
title: 根据工作流区段创建报告
seo-title: 根据工作流区段创建报告
description: 根据工作流区段创建报告
seo-description: 了解如何根据报告中的工作流细分检查交付是否成功。
page-status-flag: 从未激活
uuid: f75e005b-5328-4c98-9e78-51d54fd0e246
contentOwner: 班多
products: SG_CAMPAIGN/STANDARD
audience: 报告
content-type: 参考
topic-tags: 自定义报告
discoiquuid: b6d3de63-3add-4881-8917-04a6f8b6be4d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ea825afe573959d95d0f7f3f6e79dd38ac5a678a

---


# 根据工作流区段创建报告{#creating-a-report-workflow-segment}

在创建工作流并将人口筛选到不同的目标受众之后，您可以根据此定位工作流中定义的细分来衡量营销活动的效率。
要在报表中定位这些区段，请执行以下操作：

* [第1步：使用细分更新配置文件自定义资源](#step-1--update-profiles-custom-resource-segments)
* [第2步：创建包含区段的工作流](#step-2--create-a-workflow-segments)
* [第3步：创建动态报表以筛选区段](#step-3--create-a-dynamic-report-filter-segments)

>[!CAUTION]
>必须接受动态报告使用协议才能开始收集这些数据。
>有关本协议的详细信息，请参阅本 [页](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

## 第1步：使用细分更新配置文件自定义资源{#step-1--update-profiles-custom-resource-segments}

在报告区段代码之前，您需要更新自 **[!UICONTROL Profiles]** 定义资源以便存储区段代码。

1. 从高级菜单中，通过Adobe Campaign徽标，选择 **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom resources]**，然后选择资 **[!UICONTROL Profile (profile)]** 源。
1. 在选项 **[!UICONTROL Sending logs extension]** 卡的菜单中，选 **[!UICONTROL Data structure]** 中此选项 **[!UICONTROL Add segment code]** 可允许从定位工作流中存储区段代码并将其发送到动态报告。

   然 **[!UICONTROL Segment code]** 后，报表的维部 **[!UICONTROL Profile]** 分将提供该选项。

   ![](assets/report_segment_4.png)

1. 保存自定义资源。

1. 您现在需要发布自定义资源。
从高级菜单中，选择 **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Publishing]**。

   ![](assets/custom_profile_7.png)

1. 单 **[!UICONTROL Prepare publication]** 击，准备完毕后，单击按 **[!UICONTROL Publish]** 钮。 有关自定义资源的详细信息，请参阅此 [页](../../developing/using/updating-the-database-structure.md)。

您现在可以开始使用区段代码创建工作流。

请注意，在中启用区段代码后，将立即收集区段代码 **[!UICONTROL Sending logs extension]**。

## 第2步：创建包含区段的工作流 {#step-2--create-a-workflow-segments}

>[!NOTE]
>如果电子邮件发送的输入转换为空，则默认情况下将添加上一转换中的段代码。

您首先需要创建一个具有不同目标人群的工作流。 在此，我们希望发送一封根据受众年龄个性化的电子邮件：一个是20至30年旧档案，另一个是30至40年旧档案。

1. 创建您的工作流。 有关如何创建工作流的更多详细信息，请参阅此 [页](../../automating/using/building-a-workflow.md)。

1. 从调色板 **[!UICONTROL Query]** 中拖动活动并将其放入工作区，即可添加该活动。

1. 将20到40岁的档案定向到以后的人群，将其细分为更有针对性的人群。

   ![](assets/report_segment_1.png)

1. 添加一 **[!UICONTROL Segmentation]** 个活动，将查询结果拆分为两个目标人群。 有关细分的详细信息，请参阅此 [页](../../automating/using/targeting-data.md#segmenting-data)。

1. 双击活动 **[!UICONTROL Segmentation]** 以对其进行配置。 通过单击编辑第一个区段 **[!UICONTROL Edit properties]**。

   ![](assets/report_segment_7.png)

1. 在20到30岁之间查询配置文件，完成后 **[!UICONTROL Confirm]** 单击。

   ![](assets/report_segment_8.png)

1. 单 **[!UICONTROL Add an element]** 击以创建第二个区段，并按照上述步骤中的说明对其进行配置，以在30到40岁之间定位配置文件。

1. 编辑 **[!UICONTROL Segment code]** 要通过动态报告传递的每个人群。

   >[!NOTE]
   >此步骤是必需的，否则您将无法了解要报告的区段。

   ![](assets/report_segment_9.png)

1. 将活动拖放到 **[!UICONTROL Email delivery]** 区段之后。

   ![](assets/report_segment_3.png)

1. 根据不同的目标人群个性化您的交付。 有关电子邮件创建的详细信息，请参阅此 [页](../../designing/using/overview.md)。

1. 保存工作流。

1. 在工 **[!UICONTROL Start]** 作流准备就绪后单击。

您现在可以访问报表以跟踪区段代码。

## 第3步：创建动态报表以筛选区段 {#step-3--create-a-dynamic-report-filter-segments}

在使用工作流发送提交后，您可以使用工作流中的区段代码细分报表。

1. 在选 **[!UICONTROL Reports]** 项卡中，选择现成报告或单击按钮从头开 **[!UICONTROL Create new project]** 始创建报告。

   ![](assets/custom_profile_18.png)
1. 将维度拖放 **[!UICONTROL Delivery]** 到自由格式表中。

   ![](assets/report_segment_5.png)

1. 将不同的指标（如指标和指标）拖放 **[!UICONTROL Open]** 到表 **[!UICONTROL Click]** 中，开始筛选数据。
1. 在类别 **[!UICONTROL Dimensions]** 中，单击维度，然 **[!UICONTROL Profile]****[!UICONTROL Segment code]** 后将维度拖放到工作流的交付中，以根据目标人群来衡量电子邮件交付的成功程度。

   ![](assets/report_segment_6.png)

1. 根据需要在工作区中拖放可视化。

   ![](assets/report_segment_10.png)
