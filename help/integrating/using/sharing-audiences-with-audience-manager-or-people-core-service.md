---
solution: Campaign Standard
product: campaign
title: 使用 Audience Manager 或 People 核心服务共享受众
description: 了解如何在不同的Adobe Experience Cloud解决方案中导入或导出受众。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 2%

---


# 使用 Audience Manager 或 People 核心服务共享受众{#sharing-audiences-with-audience-manager-or-people-core-service}

## 导入受众 {#importing-an-audience}

People核心服务集成允许通过技术工作流将受众直接导入Adobe Campaign，以丰富您的数据库。 有关人员核心服务中受众共享的详细信息，请参阅此 [文档](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-publish.html)。

只有通过IMS(通过Adobe ID进行身份验证)连接的用户才能从菜单中 **[!UICONTROL Audiences]** 导入Adobe Campaign中的People核心服务的受众/区段。

1. Go to the **[!UICONTROL Audiences]** menu.
1. 在操作栏中， **[!UICONTROL Create]** 选择要在屏幕上创建受众。
1. 指定新受众的标签。
1. 将受众设 **[!UICONTROL Type]** 置为 **[!UICONTROL Experience Cloud]** 指明所创建的受众是从People核心服务导入的受众。
1. 从字 **[!UICONTROL Name of the shared audience]** 段中，选择要导入的受众。 只能导入区段。 不支持包括键值对、特征和规则在内的粒度数据。

   ![](assets/aam_import_audience.png)

1. 选择相应的 **[!UICONTROL Shared Data Source]**。

   如果选定的数据源配置为使用加密算法，则另外一个选项会优惠您可能使用的加密算法 **[!UICONTROL Force reconciliation with a profile]**。 如果数据源的字 **[!UICONTROL Channel]** 段设置为“电子邮件”或“移动”(SMS)，并且您希望利用用户档案数据，请选中此选项。

   如果您未选择，并且 **[!UICONTROL Force reconciliation with a profile]** 如果在 **[!UICONTROL Channel]** AMC数据源中设置为“电子邮件”或“移动”(SMS)，则所有已加密的声明ID都会被解密。 将创建／更 **新“文** 件”类型的受众，其中列表了所有电子邮件地址／移动电话号码。 这样，通过此集成导入共享受众时，即使活动中不存在该用户档案，也不会丢失电子邮件地址／手机号码。 请注意，此类受众不能直接使用，因为需要使用工作流手动对帐。

1. 确认创建受众。

   然后，受众通过技术工作流导入。 它由记录组成，其中ID(“访客ID”或“声明ID”)能够与用户档案维协调。 不会导入Adobe Campaign无法识别的People核心服务区段的ID。

您的受众现已导入到Adobe Campaign数据库中。 当区段直接从People核心服务或Audience Manager导入时，导入过程需要24到36小时进行同步。 在此期间后，您将能够在Adobe Campaign中查找和使用新受众。

>[!NOTE]
>
>如果要将受众从Adobe Analytics导入Adobe Campaign，则首先需要在People Core Service或Audience Manager中共享这些受众。 此过程需要12-24小时，必须与活动在24-36小时内进行同步。 在这种情况下，受众共享时间最长可达60小时。 有关People Core服务和Adobe Analytics经理中的受众受众共享的详细信息，请参阅本 [文档](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-publish.html)。

## 导出受众 {#exporting-an-audience}

受众可以使用工作流和活动从Adobe Campaign导出到Audience Manager或人员核心服务 **[!UICONTROL Save audience]** 。

它可以在新的工作流程中执行，并且只有通过IMS(通过Adobe ID进行身份验证)连接的用户才能执行。

1. 从项目、活动或营销活动的列表创建新的工作流。
1. 使用不同的可用活动目标一组用户档案。
1. 定位后，将活动拖放 **[!UICONTROL Save audience]** 到工作流中，然后打开它。
1. 选择 **[!UICONTROL Share in Adobe Experience Cloud]**。

   ![](assets/aam_save_audience_activity.png)

1. 使用字段指定受众 **[!UICONTROL Shared audience]** 符。 在打开的窗口中，您可以选择选择现有受众或创建新受众:

   * 如果您选择现有受众，则只会向受众添加新记录。
   * 要将用户档案列表导出到新受众，请填写字段，然 **[!UICONTROL Segment name]** 后在选择新 **[!UICONTROL Create]** 创建的受众之前单击。

   ![](assets/aam_save_audience_segment_picker.png)

   为了进行核对和交换，记录必须具有Adobe Experience CloudID(“访客ID”或“声明ID”)。 在导入和导出受众时，不协调的记录会被忽略。

1. 要完成，请单击屏幕右上方的复选标记。
1. 选择相应的 **[!UICONTROL Shared Data Source]**。
1. 如果您喜欢，请选 **[!UICONTROL Generate an outbound transition]** 中该框以使用导出的用户档案。 只导出可协调的用户档案。
1. 确认活动的配置并保存工作流。
1. 开始工作流以导出受众。 Adobe Campaign与人员核心服务之间的同步可能需要数小时

Adobe Campaign与人员核心服务之间的同步需要24到36小时。 在此期间，您将能够在People核心服务中找到新的受众，并在其他Adobe Experience Cloud解决方案中重复使用它。 有关在Adobe Campaign人员核心服务中使用受众共享Adobe的详细信息，请参阅本 [文档](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-audience-create.html)。

**相关主题：**

* [工作流](../../automating/using/get-started-workflows.md)
* [受众](../../audiences/using/about-audiences.md)

