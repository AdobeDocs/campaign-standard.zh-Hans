---
title: 使用 Audience Manager 或 People 核心服务共享受众
description: 了解如何在其他Adobe Experience Cloud解决方案中导入或导出受众。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: People Core Service Integration
role: Data Architect
level: Intermediate
exl-id: b0d063de-863c-42e7-98dd-c4c86da3281e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 2%

---

# 使用 Audience Manager 或 People 核心服务共享受众{#sharing-audiences-with-audience-manager-or-people-core-service}

## 导入受众 {#importing-an-audience}

People核心服务集成允许通过技术工作流将受众直接导入Adobe Campaign，以丰富您的数据库。 有关在People核心服务中共享受众的详细信息，请参阅此[文档](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html?lang=zh-Hans)。

只有通过IMS(通过Adobe ID进行身份验证)连接的用户，才能从&#x200B;**[!UICONTROL Audiences]**&#x200B;菜单导入Adobe Campaign中的人员核心服务中的受众/区段。

1. 转到&#x200B;**[!UICONTROL Audiences]**&#x200B;菜单。
1. 在操作栏中，选择要转到屏幕以创建受众的&#x200B;**[!UICONTROL Create]**。
1. 指定新受众的标签。
1. 将受众&#x200B;**[!UICONTROL Type]**&#x200B;设置为&#x200B;**[!UICONTROL Experience Cloud]**&#x200B;以指示正在创建的受众是从People核心服务导入的受众。
1. 从&#x200B;**[!UICONTROL Name of the shared audience]**&#x200B;字段中，选择要导入的受众。 只能导入区段。 不支持包含键值对、特征和规则的粒度数据。

   ![](assets/aam_import_audience.png)

1. 选择相应的&#x200B;**[!UICONTROL Shared Data Source]**。

   如果所选数据源配置为使用加密算法，则附加选项会为您提供&#x200B;**[!UICONTROL Force reconciliation with a profile]**&#x200B;的可能性。 如果数据源的&#x200B;**[!UICONTROL Channel]**&#x200B;字段设置为电子邮件或移动设备（短信），并且您想要利用配置文件数据，请选中此选项。

   如果未选择&#x200B;**[!UICONTROL Force reconciliation with a profile]**，并且在AMC数据源中将&#x200B;**[!UICONTROL Channel]**&#x200B;设置为电子邮件或移动设备(SMS)，则所有加密的已声明ID都将解密。 创建/更新了类型为&#x200B;**文件**&#x200B;的受众，其中包含所有电子邮件地址/手机号码的列表。 这样，在通过此集成导入共享受众时，即使该用户档案在Campaign中不存在，也不会丢失任何电子邮件地址/手机号码。 请注意，此类受众不能直接使用，因为它们需要使用工作流手动进行协调。

1. 确认以创建受众。

   然后，通过技术工作流导入受众。 它由能够与用户档案维度协调的ID（“访客ID”或“声明的ID”）的记录组成。 Adobe Campaign无法识别的People核心服务区段中的ID不会导入。

您的受众现已导入Adobe Campaign数据库。 直接从People核心服务或Audience Manager导入区段时，导入过程需要24-36小时才能同步。 在此时段后，您将能够在Adobe Campaign中查找和使用新受众。

>[!NOTE]
>
>如果您要将受众从Adobe Analytics导入Adobe Campaign，则需要首先在People核心服务或Audience Manager中共享这些受众。 此过程需要12-24小时，必须将其添加到与Campaign的24-36小时同步中。 在该特定情况下，受众共享时间范围最长可达60小时。 有关在People Core Service和Audience Manager中共享Adobe Analytics受众的更多信息，请参阅此[文档](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html?lang=zh-Hans)。

## 导出受众 {#exporting-an-audience}

可以使用工作流和&#x200B;**[!UICONTROL Save audience]**&#x200B;活动将受众从Adobe Campaign导出到Audience Manager或人员核心服务。

它可以在新的工作流中执行，并且只能由通过IMS(通过Adobe ID进行身份验证)连接的用户执行。

1. 从项目、营销策划或营销活动列表创建新工作流。
1. 使用不同的可用活动，定位一组用户档案。
1. 定向后，将&#x200B;**[!UICONTROL Save audience]**&#x200B;活动拖放到工作流中，然后将其打开。
1. 选择 **[!UICONTROL Share in Adobe Experience Cloud]**。

   ![](assets/aam_save_audience_activity.png)

1. 使用&#x200B;**[!UICONTROL Shared audience]**&#x200B;字段指定受众。 在打开的窗口中，您可以选择选择现有受众或创建新受众：

   * 如果选择现有受众，则只有新记录会添加到该受众。
   * 要将您的配置文件列表导出到新受众，请先填写&#x200B;**[!UICONTROL Segment name]**&#x200B;字段，然后单击&#x200B;**[!UICONTROL Create]**，然后再选择新创建的受众。

   ![](assets/aam_save_audience_segment_picker.png)

   为了进行协调和交换，记录必须具有Adobe Experience Cloud ID（“访客ID”或“声明的ID”）。 导入和导出受众时会忽略未协调的记录。

1. 要完成，请单击屏幕右上方的复选标记。
1. 选择相应的&#x200B;**[!UICONTROL Shared Data Source]**。
1. 如果需要，请选中&#x200B;**[!UICONTROL Generate an outbound transition]**&#x200B;框以使用导出的用户档案。 仅导出可协调的配置文件。
1. 确认活动的配置并保存工作流。
1. 启动工作流以导出受众。 Adobe Campaign与People核心服务之间的同步可能需要几个小时

Adobe Campaign与People核心服务之间的同步需要24-36小时。 在此时段后，您将能够在People核心服务中找到新受众，并在其他Adobe Experience Cloud解决方案中重复使用它。 有关在Adobe人员核心服务中使用Adobe Campaign共享受众的更多信息，请参阅此[文档](https://experienceleague.adobe.com/docs/core-services/interface/audiences/t-audience-create.html?lang=zh-Hans)。

**相关主题：**

* [工作流](../../automating/using/get-started-workflows.md)
* [受众](../../audiences/using/about-audiences.md)
