---
solution: Campaign Standard
product: campaign
title: 定向 Adobe Experience Platform 受众
description: 了解如何在工作流内目标Adobe Experience Platform受众。
audience: automating
content-type: reference
topic-tags: channel-activities
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 5%

---


# 定向 Adobe Experience Platform 受众 {#targeting-aep-audiences}

>[!IMPORTANT]
>
>受众目标服务目前处于测试阶段，可能会在不通知的情况下频繁进行更新。 客户必须托管在Azure上（目前仅限北美的beta版），才能访问这些功能。 如果您想要访问，请联系Adobe客户服务中心。

使用Segment Builder创建 [Adobe Experience Platform受众](../../audiences/using/aep-about-audience-destinations-service.md) 后，您可以像在工作流内部创建活动受众那样使用来个性化和发送消息。

要在您的工作流中激活Adobe Experience Platform受众，请执行以下步骤：

1. 在工作流 **[!UICONTROL Read audience]** 中添加活动，然后将其打开。

1. 选择下 **[!UICONTROL Adobe Experience Platform]** 面的选 **[!UICONTROL Type of audience]**&#x200B;项，然后添加所需的受众。

   ![](assets/aep_wkf_readaudience.png)

1. （可选）选择受众后，您可以单击眼睛按钮来查看和／或编辑区段定义（确保再次保存更改）。

   单击“眼睛”按钮将直接转到与活动内选定受众关联的“区段生成器”（在另一个选项卡中）。

1. 选择一 **[!UICONTROL Platform data mapping]** 个元素，为选定的Adobe Experience Platform定位维度指定所需的受众。

   默认情况下，用于对帐的主键(例如，用户档案表的iRecipientID、AppSubscription表的iAppSubscriptionID)将从下拉列表自动可用。 要在主键之外目标，必须创建自定义 **命名空间**。

   >[!NOTE]
   >
   >对于主键外的目标，还必须创建与自定义目标映射对应的自定义命名空间。 For more information on Target Mapping, refer to [this section](../../administration/using/target-mappings-in-campaign.md).

   ![](assets/aep_wkf_readaudience_namespace.png)

   此列表包含已在实例上配置的所有体验数据模型(XDM)映射。 有关Adobe Experience Platform数据连接器的详细信息，请参 [阅此专用文档](../../developing/using/aep-about-data-connector.md)。

   ![](assets/aep_wkf_readaudience_namespace2.png)

1. 正确配置受众和定位维度后，单击 **[!UICONTROL Confirm]** 按钮以保存更改。

您现在可以配置与其他活动的工作流。 例如，您可以链接活动 **[!UICONTROL Email delivery]** 以向已选定的受众发送电子邮件。

![](assets/aep_wkf_email.png)

>[!NOTE]
>
>Campaign Standard允许您目标所有投放渠道中的Adobe Experience Platform受众:电子邮件、SMS消息、直接邮件消息、推送通知和应用程序内消息。
>
>*注意：对于所有推送和应用程序内消息，Campaign Standard仅支持已知用户档案的投放。

有关如何使用工作流和投放的详细信息，请参阅以下部分：

* [了解工作流](../../automating/using/get-started-workflows.md)
* [构建工作流](../../automating/using/building-a-workflow.md)
* [了解通信渠道](../../channels/using/get-started-communication-channels.md)
* [关于渠道活动](../../automating/using/about-channel-activities.md)
