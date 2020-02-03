---
title: 面向Adobe Experience Platform受众
description: 了解如何在工作流程中定位Adobe Experience PL以吸引受众。
page-status-flag: never-activated
uuid: 528d9472-e447-47af-a6b2-3181aa5fb5ad
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 19796aca-6e9e-4d3a-8917-ba660ec7993c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1059b840d9a2d0c89a6cbd1808b645862747a76c

---


# 面向Adobe Experience Platform受众 {#targeting-aep-audiences}

>[!IMPORTANT]
>
>受众目标服务目前处于测试阶段，可能会在不另行通知的情况下频繁进行更新。 客户必须托管在Azure上（目前仅针对北美）才能访问这些功能。 如果您希望访问，请联系Adobe客户关怀。

使用统一的Profile区段构建器创建 [Adobe Experience Platform受众后](../../audiences/using/aep-about-audience-destinations-service.md) ，您可以像在工作流中对Campaign受众进行个性化和发送消息一样使用它。

要将Adobe Experience platform受众激活到您的工作流中，请执行以下步骤：

1. 将活动 **[!UICONTROL Read audience]**添加到工作流中，然后将其打开。

1. 选择下 **[!UICONTROL Adobe Experience Platform]**方的选**[!UICONTROL Type of audience]**&#x200B;项，然后添加所需的受众。

   ![](assets/aep_wkf_readaudience.png)

1. （可选）选择受众后，您可以单击眼睛按钮来查看和／或编辑区段定义（确保再次保存更改）。

   单击“眼睛”按钮只需将您定向到与营销活动中选定受众关联的“统一区段生成器”（在另一个选项卡中）。

1. 选择一 **[!UICONTROL Platform data mapping]**个元素，为选定的Adobe Experience Platform受众指定所需的定位维度。

   默认情况下，用于协调的主键（例如，“配置文件”表的iRecipientID、“AppSubscription”表的iAppSubscriptionID）将从下拉列表中自动可用。 要在主键之外定位，必须创建自定义命名空 **间**。

   >[!NOTE]
   >
   >对于主键外的目标，您还必须创建与自定义命名空间对应的自定义目标映射。 For more information on Target Mapping, refer to [this section](../../administration/using/target-mappings-in-campaign.md).

   ![](assets/aep_wkf_readaudience_namespace.png)

   此列表包含在实例上配置的所有体验数据模型(XDM)映射。 有关Adobe Experience Platform Data Connector的详细信息，请参阅 [此专用文档](../../administration/using/aep-about-data-connector.md)。

   ![](assets/aep_wkf_readaudience_namespace2.png)

1. 正确配置受众和定位维后，单击按 **[!UICONTROL Confirm]**钮以保存更改。

您现在可以配置包含其他活动的工作流。 例如，您可以链接活动 **[!UICONTROL Email delivery]**以向已选择的受众发送电子邮件。

![](assets/aep_wkf_email.png)

>[!NOTE]
>
>Campaign Standard可让您在所有交付渠道中定位Adobe Experience Platform受众：电子邮件、SMS消息、直邮消息、推送通知和应用程序内消息。

有关如何使用工作流和交付的详细信息，请参阅以下部分：

* [了解工作流](../../automating/using/discovering-workflows.md)
* [构建工作流](../../automating/using/building-a-workflow.md)
* [了解通信渠道](../../channels/using/discovering-communication-channels.md)
* [关于渠道活动](../../automating/using/about-channel-activities.md)
