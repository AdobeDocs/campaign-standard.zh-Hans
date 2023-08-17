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
source-wordcount: '801'
ht-degree: 2%

---

# 使用 Audience Manager 或 People 核心服务共享受众{#sharing-audiences-with-audience-manager-or-people-core-service}

## 导入受众 {#importing-an-audience}

People核心服务集成允许通过技术工作流将受众直接导入Adobe Campaign，以丰富您的数据库。 有关在People核心服务中共享受众的详细信息，请参阅此 [文档](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html).

在Adobe Campaign中，可从“人员”核心服务导入受众/区段 **[!UICONTROL Audiences]** 菜单仅由通过IMS(通过Adobe ID进行身份验证)连接的用户使用。

1. 转到 **[!UICONTROL Audiences]** 菜单。
1. 在操作栏中，选择 **[!UICONTROL Create]** 将转到屏幕以创建受众。
1. 指定新受众的标签。
1. 设置受众 **[!UICONTROL Type]** 到 **[!UICONTROL Experience Cloud]** 指示正在创建的受众是从People核心服务导入的受众。
1. 从 **[!UICONTROL Name of the shared audience]** 字段中，选择要导入的受众。 只能导入区段。 不支持包含键值对、特征和规则的粒度数据。

   ![](assets/aam_import_audience.png)

1. 选择相应的 **[!UICONTROL Shared Data Source]**.

   如果所选数据源配置为使用加密算法，则还可以使用其他选项来 **[!UICONTROL Force reconciliation with a profile]**. 如果符合以下条件，请选中此选项 **[!UICONTROL Channel]** 数据源的字段设置为电子邮件或移动设备(SMS)，并且您想要利用用户档案数据。

   如果您不选择 **[!UICONTROL Force reconciliation with a profile]** 和if **[!UICONTROL Channel]** 在AMC数据源中设置为电子邮件或移动设备(SMS)，然后解密所有加密的声明ID。 受众类型 **文件** 创建/更新包含所有电子邮件地址/手机号码的列表。 这样，在通过此集成导入共享受众时，即使该用户档案在Campaign中不存在，也不会丢失任何电子邮件地址/手机号码。 请注意，此类受众不能直接使用，因为它们需要使用工作流手动进行协调。

1. 确认以创建受众。

   然后，通过技术工作流导入受众。 它由能够与用户档案维度协调的ID（“访客ID”或“声明的ID”）的记录组成。 Adobe Campaign无法识别的People核心服务区段中的ID不会导入。

您的受众现已导入Adobe Campaign数据库。 直接从People核心服务或Audience Manager导入区段时，导入过程需要24-36小时才能同步。 在此时段后，您将能够在Adobe Campaign中查找和使用新受众。

>[!NOTE]
>
>如果您要将受众从Adobe Analytics导入Adobe Campaign，则需要首先在People核心服务或Audience Manager中共享这些受众。 此过程需要12-24小时，必须将其添加到与Campaign的24-36小时同步中。 在该特定情况下，受众共享时间范围最长可达60小时。 有关在People Core Service和Audience Manager中共享Adobe Analytics受众的更多信息，请参阅此 [文档](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html).

## 导出受众 {#exporting-an-audience}

可以使用工作流和，将受众从Adobe Campaign导出到Audience Manager或人员核心服务。 **[!UICONTROL Save audience]** 活动。

它可以在新的工作流中执行，并且只能由通过IMS(通过Adobe ID进行身份验证)连接的用户执行。

1. 从项目、营销策划或营销活动列表创建新工作流。
1. 使用不同的可用活动，定位一组用户档案。
1. 定向后，拖放 **[!UICONTROL Save audience]** 活动添加到工作流中，然后将其打开。
1. 选择 **[!UICONTROL Share in Adobe Experience Cloud]**。

   ![](assets/aam_save_audience_activity.png)

1. 使用指定受众 **[!UICONTROL Shared audience]** 字段。 在打开的窗口中，您可以选择选择现有受众或创建新受众：

   * 如果选择现有受众，则只有新记录会添加到该受众。
   * 要将您的配置文件列表导出到新受众，请完成 **[!UICONTROL Segment name]** 字段，然后单击 **[!UICONTROL Create]** ，然后再选择新创建的受众。

   ![](assets/aam_save_audience_segment_picker.png)

   为了进行协调和交换，记录必须具有Adobe Experience Cloud ID（“访客ID”或“声明的ID”）。 导入和导出受众时会忽略未协调的记录。

1. 要完成，请单击屏幕右上方的复选标记。
1. 选择相应的 **[!UICONTROL Shared Data Source]**.
1. 如果您愿意，请查看 **[!UICONTROL Generate an outbound transition]** 框以使用已导出的配置文件。 仅导出可协调的配置文件。
1. 确认活动的配置并保存工作流。
1. 启动工作流以导出受众。 Adobe Campaign与People核心服务之间的同步可能需要几个小时

Adobe Campaign与People核心服务之间的同步需要24-36小时。 在此时段后，您将能够在People核心服务中找到新受众，并在其他Adobe Experience Cloud解决方案中重复使用它。 有关在Adobe人员核心服务中使用Adobe Campaign共享受众的更多信息，请参阅此 [文档](https://experienceleague.adobe.com/docs/core-services/interface/audiences/t-audience-create.html).

**相关主题：**

* [工作流](../../automating/using/get-started-workflows.md)
* [受众](../../audiences/using/about-audiences.md)
