---
title: 使用 Audience Manager 或 People 核心服务共享受众
description: 了解如何在不同的Adobe Experience cloud解决方案中导入或导出受众。
page-status-flag: 从未激活
uuid: a3701e72-5846-4241-afee-d713b499a27a
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 集成
content-type: 参考
topic-tags: 使用Campaign和Audience manager或People核心服务
discoiquuid: 77af0772-52b5-46bc-a964-675b4596524
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 使用 Audience Manager 或 People 核心服务共享受众{#sharing-audiences-with-audience-manager-or-people-core-service}

## 导入受众 {#importing-an-audience}

People核心服务集成允许通过技术工作流将受众直接导入Adobe Campaign以丰富您的数据库。 有关人员核心服务中的受众共享的更多信息，请参阅此 [文档](https://marketing.adobe.com/resources/help/en_US/mcloud/t_publish_audience_segment.html)。

从Adobe Campaign中的People核心服务导入受众／区段只能由通过IMS连接的用户(通 **[!UICONTROL Audiences]** 过Adobe ID进行身份验证)从菜单执行。

1. 转到菜 **[!UICONTROL Audiences]** 单。
1. 在操作栏中，选 **[!UICONTROL Create]** 择要在屏幕上创建受众。
1. 指定新受众的标签。
1. 将受众设 **[!UICONTROL Type]** 置为指 **[!UICONTROL Experience Cloud]** 明所创建的受众是从“人员”核心服务导入的受众。
1. 从字段 **[!UICONTROL Name of the shared audience]** 中，选择要导入的受众。 只能导入区段。 不支持包括键值对、特征和规则在内的粒度数据。

   ![](assets/aam_import_audience.png)

1. 选择相应的 **[!UICONTROL Shared Data Source]**。

   如果选定的数据源配置为使用加密算法，则还有一个其他选项为您提供使用加密算法的可能性 **[!UICONTROL Force reconciliation with a profile]**。 如果数据源的字 **[!UICONTROL Channel]** 段设置为“电子邮件”或“移动”(SMS)，并且您希望利用配置文件数据，请选中此选项。

   如果您未选择，并且 **[!UICONTROL Force reconciliation with a profile]** 如果在AMC数据源 **[!UICONTROL Channel]** 中设置为“电子邮件”或“移动”(SMS)，则所有已加密的已声明ID都将被解密。 将创建／更 **新“文件** ”类型的受众，其中包含所有电子邮件地址／手机号码的列表。 这样，通过此集成导入共享受众时不会丢失电子邮件地址／手机号码，即使该配置文件在Campaign中不存在也是如此。 请注意，此类受众不能直接使用，因为需要使用工作流手动调节它们。

1. 确认创建受众。

   然后，受众会通过技术工作流导入。 它由记录组成，其中ID（“访客ID”或“声明ID”）能够与配置文件维度协调。 不会导入Adobe Campaign无法识别的People核心服务区段的ID。

您的受众现在已导入到Adobe Campaign数据库中。 从People核心服务或Audience manager直接导入区段时，导入过程需要24到36小时才能同步。 在此期间后，您将能够在Adobe Campaign中查找和使用您的新受众。

>[!NOTE]
>
>如果要将受众从Adobe Analytics导入Adobe Campaign，则首先需要在People Core service或Audience manager中共享这些受众。 此过程需要12-24小时，必须将其添加到与Campaign的24-36小时同步中。 在这种情况下，受众共享的时间范围最长可达60小时。 有关People Core服务和Audience Manager中Adobe Analytics受众共享的更多信息，请参阅此 [文档](https://marketing.adobe.com/resources/help/en_US/mcloud/t_publish_audience_segment.html)。

## 导出受众 {#exporting-an-audience}

可以使用工作流和活动将受众从Adobe Campaign导出到Audience Manager或People核心服 **[!UICONTROL Save audience]** 务。

它只能在新的工作流程中执行，并且只能由通过IMS（通过Adobe ID进行身份验证）连接的用户执行。

1. 从计划、营销活动或营销活动列表创建新的工作流。
1. 使用可用的不同活动，定位一组配置文件。
1. 定位后，将活动拖放到工 **[!UICONTROL Save audience]** 作流中，然后打开它。
1. Select **[!UICONTROL Share in Adobe Experience Cloud]**.

   ![](assets/aam_save_audience_activity.png)

1. 使用字段指定受 **[!UICONTROL Shared audience]** 众。 在打开的窗口中，您可以选择选择现有受众或创建新受众：

   * 如果您选择现有受众，则只会向受众添加新记录。
   * 要将您的个人资料列表导出到新受众，请填写字段，然 **[!UICONTROL Segment name]** 后在选择新创 **[!UICONTROL Create]** 建的受众之前单击。
   ![](assets/aam_save_audience_segment_picker.png)

   为了进行核对和交换，这些记录必须具有Adobe Experience Cloud ID（“访客ID”或“声明ID”）。 导入和导出受众时，不协调的记录会被忽略。

1. 要完成该操作，请单击屏幕右上方的复选标记。
1. 选择相应的 **[!UICONTROL Shared Data Source]**。
1. 如果需要，请选中该 **[!UICONTROL Generate an outbound transition]** 框以使用导出的配置文件。 只导出可协调的配置文件。
1. 确认活动的配置并保存工作流。
1. 启动您的工作流以导出受众。 Adobe Campaign与People核心服务之间的同步可能需要数小时

Adobe Campaign与People核心服务之间的同步需要24-36小时。 在此期间后，您将能够在People核心服务中找到新的受众，并在其他Adobe Experience cloud解决方案中重复使用它。 有关在Adobe People核心服务中使用Adobe Campaign共享受众的更多信息，请参阅此 [文档](https://marketing.adobe.com/resources/help/en_US/mcloud/t_audience_create.html)。

**相关主题：**

* [工作流](../../automating/using/workflow-data-and-processes.md)
* [受众](../../audiences/using/about-audiences.md)

