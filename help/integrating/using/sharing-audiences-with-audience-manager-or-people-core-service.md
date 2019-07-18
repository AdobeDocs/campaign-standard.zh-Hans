---
title: 使用Audience Manager或People核心服务共享受众
seo-title: 使用Audience Manager或People核心服务共享受众
description: 使用Audience Manager或People核心服务共享受众
seo-description: 了解如何在不同的Adobe Experience Cloud解决方案中导入或导出受众。
page-status-flag: 从未激活
uuid: a3701e72-5846-4241-afee-d713 b499 a27 a
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 集成
content-type: reference
topic-tags: publishing-with-campaign-and-operators-manager-or-ople-core-service
discoiquuid: 77af0772-52b5-46bc-a964-675b45965524
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Sharing audiences with Audience Manager or People core service{#sharing-audiences-with-audience-manager-or-people-core-service}

## Importing an audience {#importing-an-audience}

用户核心服务集成允许通过技术工作流程直接将受众导入Adobe Campaign，从而丰富数据库。For more information on audience sharing in People core service, refer to this [documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/t_publish_audience_segment.html).

Importing audiences/segments from People core service in Adobe Campaign can be carried out from the **[!UICONTROL Audiences]** menu only by users connected via IMS (authentication via Adobe ID).

1. Go to the **[!UICONTROL Audiences]** menu.
1. In the action bar, select **[!UICONTROL Create]** to be taken to the screen to create an audience.
1. 指定新受众的标签。
1. Set the audience **[!UICONTROL Type]** to **[!UICONTROL Experience Cloud]** to indicate that the audience being created is an audience that was imported from People core service.
1. From the **[!UICONTROL Name of the shared audience]** field, select the audience to import. 只能导入区段。不支持粒度数据，包括键值对、特征和规则。

   ![](assets/aam_import_audience.png)

1. Select the corresponding **[!UICONTROL Shared Data Source]**.

   If the selected data source is configured to use an encryption algorithm, an additional option offers you the possibility to **[!UICONTROL Force reconciliation with a profile]**. Check this option if the **[!UICONTROL Channel]** field of the data source is set to Email or Mobile (SMS) and if you want to leverage profile data.

   If you do not select the **[!UICONTROL Force reconciliation with a profile]** and if **[!UICONTROL Channel]** is set in AMC Data source to Email or Mobile (SMS) then all the encrypted declared IDs are decrypted. An audience of type **File** with a list of all the email addresses/mobile phone numbers is created/updated. 这样，即使在Campaign中不存在该配置文件，电子邮件地址/移动电话号码也不会在通过此集成导入共享受众时丢失。请注意，这类受众不能直接使用，因为他们需要使用工作流手动进行调解。

1. 确认创建受众。

   然后通过技术工作流程导入受众。它由ID('访问者ID'或'声明ID')能够与配置文件维度协调的记录组成。不会导入来自Adobe Campaign未识别的人员核心服务区段的ID。

受众现在已导入到Adobe Campaign数据库中。从People核心服务或Audience Manager直接导入区段时，导入过程需要24-36小时才能同步。此后，您将能够在Adobe Campaign中查找和使用新受众。

>[!NOTE]
>
>如果您要将受众从Adobe Analytics导入Adobe Campaign，则需要首先在People Core Service或Audience Manager中共享这些受众。此过程需要12-24小时，必须将其添加到与Campaign同步的24-36小时。在这种特定情况下，受众共享时间范围最长可能长达60小时。For more information on Adobe Analytics audience sharing in People Core service and Audience manager, refer to this [documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/t_publish_audience_segment.html).

## Exporting an audience {#exporting-an-audience}

An audience can be exported from Adobe Campaign to Audience Manager or People core service using a workflow and the **[!UICONTROL Save audience]** activity.

它可以在新工作流程中执行，只由通过IMS连接的用户(通过Adobe ID进行身份验证)进行。

1. 从计划、营销活动或营销活动列表创建新工作流程。
1. 使用可用的不同活动，定位一组配置文件。
1. After the targeting, drag and drop a **[!UICONTROL Save audience]** activity into the workflow, then open it.
1. Select **[!UICONTROL Share in Adobe Experience Cloud]**.

   ![](assets/aam_save_audience_activity.png)

1. Specify the audience using the **[!UICONTROL Shared audience]** field. 在打开的窗口中，您可以选择选择现有受众或创建新受众：

   * 如果您选择现有受众，则只会向受众添加新记录。
   * To export your profile list into a new audience, complete the **[!UICONTROL Segment name]** field then click **[!UICONTROL Create]** before selecting the newly created audience.
   ![](assets/aam_save_audience_segment_picker.png)

   为了进行协调和交换，记录必须具有Adobe Experience Cloud ID('访问者ID'或“声明ID”)。导入和导出受众时忽略未协调的记录。

1. 完成后，单击屏幕右上角的复选标记。
1. Select the corresponding **[!UICONTROL Shared Data Source]**.
1. If you like, check the **[!UICONTROL Generate an outbound transition]** box to use the profiles that were exported. 只导出可协调的配置文件。
1. 确认活动的配置并保存您的工作流。
1. 开始工作流程以导出受众。Adobe Campaign与人员核心服务之间的同步可能需要几个小时

Adobe Campaign与People核心服务之间的同步需要24-36小时。此后，您将能够在People核心服务中找到新受众，并在其他Adobe Experience Cloud解决方案中重复使用它。For more information on using an Adobe Campaign shared audience in Adobe People core service, refer to this [documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/t_audience_create.html).

**相关主题：**

* [工作流](../../automating/using/workflow-data-and-processes.md)
* [受众受众](../../audiences/using/about-audiences.md)

