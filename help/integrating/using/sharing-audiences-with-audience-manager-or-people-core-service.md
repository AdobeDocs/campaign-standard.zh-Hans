---
solution: Campaign Standard
product: campaign
title: 使用 Audience Manager 或 People 核心服务共享受众
description: 了解如何在不同的Adobe Experience Cloud解决方案中导入或导出您的受众。
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

## 导入受众{#importing-an-audience}

People核心服务集成允许通过技术工作流将受众直接导入Adobe Campaign，以丰富您的数据库。 有关People核心服务中受众共享的详细信息，请参阅此[文档](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-publish.html)。

从Adobe Campaign中的People核心服务导入受众/区段只能由通过IMS(通过Adobe ID进行身份验证)连接的用户从&#x200B;**[!UICONTROL Audiences]**&#x200B;菜单执行。

1. 转到&#x200B;**[!UICONTROL Audiences]**&#x200B;菜单。
1. 在操作栏中，选择&#x200B;**[!UICONTROL Create]**&#x200B;以将其应用于屏幕以创建受众。
1. 指定新受众的标签。
1. 将受众&#x200B;**[!UICONTROL Type]**&#x200B;设置为&#x200B;**[!UICONTROL Experience Cloud]**，以指示所创建的受众是从People核心服务中导入的受众。
1. 从&#x200B;**[!UICONTROL Name of the shared audience]**&#x200B;字段中，选择要导入的受众。 只能导入区段。 不支持包括键值对、特征和规则在内的粒度数据。

   ![](assets/aam_import_audience.png)

1. 选择相应的&#x200B;**[!UICONTROL Shared Data Source]**。

   如果选定的数据源配置为使用加密算法，则附加选项会优惠您&#x200B;**[!UICONTROL Force reconciliation with a profile]**&#x200B;的可能性。 如果数据源的&#x200B;**[!UICONTROL Channel]**&#x200B;字段设置为“电子邮件”或“移动”(SMS)，并且您希望利用用户档案数据，请选中此选项。

   如果您未选择&#x200B;**[!UICONTROL Force reconciliation with a profile]**，并且如果在AMC数据源中将&#x200B;**[!UICONTROL Channel]**&#x200B;设置为“电子邮件”或“移动”(SMS)，则所有加密的声明ID都将被解密。 创建/更新类型为&#x200B;**File**&#x200B;的受众,列表所有电子邮件地址/移动电话号码。 这样，即使活动中不存在共享受众，通过此集成导入共享用户档案时也不会丢失电子邮件地址/手机号码。 请注意，此类受众无法直接使用，因为需要使用工作流手动对帐。

1. 确认创建受众。

   然后，将通过技术工作流导入受众。 它由记录组成，其中ID(“访客ID”或“声明ID”)能够与用户档案维度协调。 不会导入Adobe Campaign无法识别的People核心服务区段的ID。

您的受众现在已导入到Adobe Campaign数据库中。 从People核心服务或Audience Manager直接导入区段时，导入过程需要24-36小时才能同步。 在此期间后，您将能够在Adobe Campaign中查找和使用新受众。

>[!NOTE]
>
>如果要将受众从Adobe Analytics导入到Adobe Campaign，则首先需要在People Core Service或Audience Manager中共享这些受众。 此过程需要12-24小时，必须与活动同步24-36小时。 在这种情况下，受众共享时间最长可达60小时。 有关People Core服务和受众管理器中Adobe Analytics受众共享的详细信息，请参阅此[文档](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-publish.html)。

## 导出受众{#exporting-an-audience}

可以使用工作流和&#x200B;**[!UICONTROL Save audience]**&#x200B;受众将活动从Adobe Campaign导出到Audience Manager或People核心服务。

它可以在新的工作流程中执行，并且只能由通过IMS(通过Adobe ID进行身份验证)连接的用户执行。

1. 从项目、活动或营销活动的列表创建新工作流。
1. 使用可用的不同活动目标一组用户档案。
1. 定位后，将&#x200B;**[!UICONTROL Save audience]**&#x200B;活动拖放到工作流中，然后打开它。
1. 选择 **[!UICONTROL Share in Adobe Experience Cloud]**。

   ![](assets/aam_save_audience_activity.png)

1. 使用&#x200B;**[!UICONTROL Shared audience]**&#x200B;字段指定受众。 在打开的窗口中，您可以选择选择现有受众或创建新受众:

   * 如果您选择现有受众，则只会向受众添加新记录。
   * 要将用户档案列表导出到新受众，请填写&#x200B;**[!UICONTROL Segment name]**&#x200B;字段，然后单击&#x200B;**[!UICONTROL Create]**，然后选择新创建的受众。

   ![](assets/aam_save_audience_segment_picker.png)

   为了进行协调和交换，这些记录必须具有Adobe Experience Cloud ID(“访客ID”或“声明ID”)。 在导入和导出受众时，将忽略未协调的记录。

1. 要完成，请单击屏幕右上角的复选标记。
1. 选择相应的&#x200B;**[!UICONTROL Shared Data Source]**。
1. 如果需要，请选中&#x200B;**[!UICONTROL Generate an outbound transition]**&#x200B;框以使用导出的用户档案。 只导出可协调的用户档案。
1. 确认活动的配置并保存工作流。
1. 开始工作流以导出受众。 Adobe Campaign与人员核心服务之间的同步可能需要数小时

Adobe Campaign与人员核心服务之间的同步需要24-36小时。 在此期间之后，您将能够在People核心服务中找到新的受众，并在其他Adobe Experience Cloud解决方案中重复使用它。 有关在Adobe People核心服务中使用Adobe Campaign共享受众的详细信息，请参阅此[文档](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-audience-create.html)。

**相关主题：**

* [工作流](../../automating/using/get-started-workflows.md)
* [受众](../../audiences/using/about-audiences.md)

