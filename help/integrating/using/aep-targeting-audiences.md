---
title: 定位 Adobe Experience Platform 受众
description: 了解如何在工作流中定位Adobe Experience Platform受众。
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 11e2cd7e-99b7-45cc-a0c2-41049128fe49
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 5%

---

# 定位 Adobe Experience Platform 受众 {#targeting-aep-audiences}

>[!IMPORTANT]
>
>Audience Destinations服务目前处于测试阶段，可能会频繁更新，恕不另行通知。 需要在Azure上托管客户（目前仅适用于北美地区的测试版）才能访问这些功能。 如果您希望访问，请联系Adobe客户关怀团队。

创建 [Adobe Experience Platform受众](../../integrating/using/aep-about-audience-destinations-service.md) 使用区段生成器，您可以像工作流中的Campaign受众一样使用区段生成器，以个性化和发送消息。

要在工作流中激活Adobe Experience Platform受众，请执行以下步骤：

1. 添加 **[!UICONTROL Read audience]** 活动放入工作流中，然后将其打开。

1. 选择 **[!UICONTROL Adobe Experience Platform]** 选项 **[!UICONTROL Type of audience]**，然后添加所需的受众。

   ![](assets/aep_wkf_readaudience.png)

1. （可选）选择受众后，您可以单击眼睛按钮以查看和/或编辑区段定义（确保再次保存更改）。

   单击眼睛按钮只需将您定向到与Campaign中选定受众关联的区段生成器（位于另一个选项卡中）。

1. 选择 **[!UICONTROL Platform data mapping]** 元素来为选定的Adobe Experience Platform受众指定所需的定向维度。

   默认情况下，用于协调的主键（例如，用于配置文件表的iRecipientID、用于AppSubscription表的iAppSubscriptionID）将从下拉列表中自动可用。 要在主键之外定位，必须创建自定义 **命名空间**.

   >[!NOTE]
   >
   >对于主键值以外的目标，还必须创建与自定义命名空间对应的自定义目标映射。 有关目标映射的更多信息，请参阅 [此部分](../../administration/using/target-mappings-in-campaign.md).

   ![](assets/aep_wkf_readaudience_namespace.png)

   此列表包含在实例中配置的所有体验数据模型(XDM)映射。 有关Adobe Experience Platform Data Connector的更多信息，请参阅 [本专用文档](../../integrating/using/aep-about-data-connector.md).

   ![](assets/aep_wkf_readaudience_namespace2.png)

1. 正确配置受众和定向维度后，单击 **[!UICONTROL Confirm]** 按钮以保存更改。

您现在可以使用其他活动配置工作流。 例如，您可以将 **[!UICONTROL Email delivery]** 活动，向已选定的受众发送电子邮件。

![](assets/aep_wkf_email.png)

>[!NOTE]
>
>Campaign Standard允许您在所有交付渠道中定位Adobe Experience Platform受众：电子邮件、短信消息、直邮消息、推送通知和应用程序内消息。
>
>*注意：对于所有推送消息和应用程序内消息，Campaign Standard仅支持已知用户档案的投放。

有关如何使用工作流和投放的更多信息，请参阅以下章节：

* [了解工作流](../../automating/using/get-started-workflows.md)
* [构建工作流](../../automating/using/building-a-workflow.md)
* [了解通信渠道](../../channels/using/get-started-communication-channels.md)
* [关于渠道活动](../../automating/using/about-channel-activities.md)
