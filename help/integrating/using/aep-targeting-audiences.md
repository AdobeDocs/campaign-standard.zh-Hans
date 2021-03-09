---
solution: Campaign Standard
product: campaign
title: 定向 Adobe Experience Platform 受众
description: 了解如何在工作流中目标Adobe Experience Platform受众。
audience: automating
content-type: reference
topic-tags: channel-activities
translation-type: tm+mt
source-git-commit: 35d61efce8d752ea30b7eaad55e6c23d4debd853
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 5%

---


# 定向 Adobe Experience Platform 受众 {#targeting-aep-audiences}

>[!IMPORTANT]
>
>受众目标服务目前处于测试阶段，可能会在不通知的情况下频繁进行更新。 客户需要托管在Azure上（目前仅针对北美）才能访问这些功能。 如果您希望访问，请联系Adobe客户关怀团队。

使用区段生成器创建[Adobe Experience Platform受众](../../integrating/using/aep-about-audience-destinations-service.md)后，您可以像在工作流内对活动受众进行个性化和发送消息一样使用它。

要将Adobe Experience Platform受众激活到工作流中，请执行以下步骤：

1. 在工作流中添加&#x200B;**[!UICONTROL Read audience]**&#x200B;活动，然后将其打开。

1. 选择&#x200B;**[!UICONTROL Type of audience]**&#x200B;下的&#x200B;**[!UICONTROL Adobe Experience Platform]**&#x200B;选项，然后添加所需的受众。

   ![](assets/aep_wkf_readaudience.png)

1. （可选）选择受众后，您可以单击眼睛按钮来查看和/或编辑区段定义（确保再次保存更改）。

   单击“眼睛”按钮只需将您定向到与活动中选定受众关联的区段生成器（在另一个选项卡中）。

1. 选择&#x200B;**[!UICONTROL Platform data mapping]**&#x200B;元素，为选定的Adobe Experience Platform受众指定所需的定位维度。

   默认情况下，用于协调的主键(例如，用户档案表的iRecipientID、AppSubscription表的iAppSubscriptionID)将从下拉列表自动可用。 要在主键之外目标，必须创建自定义&#x200B;**命名空间**。

   >[!NOTE]
   >
   >对于主键外的目标，还必须创建与自定义目标映射对应的自定义命名空间。 有关目标映射的详细信息，请参阅[本节](../../administration/using/target-mappings-in-campaign.md)。

   ![](assets/aep_wkf_readaudience_namespace.png)

   此列表包含已在实例上配置的所有体验数据模型(XDM)映射。 有关Adobe Experience Platform Data Connector的详细信息，请参阅[此专用文档](../../integrating/using/aep-about-data-connector.md)。

   ![](assets/aep_wkf_readaudience_namespace2.png)

1. 正确配置受众和定位维度后，单击&#x200B;**[!UICONTROL Confirm]**&#x200B;按钮以保存更改。

您现在可以使用其他活动配置您的工作流。 例如，您可以链接&#x200B;**[!UICONTROL Email delivery]**&#x200B;活动，向已选择的受众发送电子邮件。

![](assets/aep_wkf_email.png)

>[!NOTE]
>
>Campaign Standard允许您在所有投放渠道中目标Adobe Experience Platform受众:电子邮件、SMS消息、直接邮件消息、推送通知和应用程序内消息。
>
>*注意：对于所有推送和应用程序内消息，Campaign Standard仅支持已知用户档案的投放。

有关如何使用工作流和投放的详细信息，请参阅以下部分：

* [了解工作流](../../automating/using/get-started-workflows.md)
* [构建工作流](../../automating/using/building-a-workflow.md)
* [了解通信渠道](../../channels/using/get-started-communication-channels.md)
* [关于渠道活动](../../automating/using/about-channel-activities.md)
