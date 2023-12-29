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
hide: true
hidefromtoc: true
source-git-commit: 110f3ccb5865e70c78e18485b4ff4ba7a648af3f
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 3%

---

# 定位 Adobe Experience Platform 受众 {#targeting-aep-audiences}

>[!IMPORTANT]
>
>Audience Destinations服务当前为测试版，可能会频繁更新，恕不另行通知。 客户需要在Azure上托管（目前为仅北美测试版）才能访问这些功能。 如果您希望获得访问权限，请联系Adobe客户关怀团队。

创建 [Adobe Experience Platform受众](../../integrating/using/aep-about-audience-destinations-service.md) 通过使用区段生成器，您可以像在工作流中用于营销活动受众一样使用该区段来个性化和发送消息。

要在工作流中激活Adobe Experience Platform受众，请执行以下步骤：

1. 添加 **[!UICONTROL Read audience]** 活动添加到工作流中，然后将其打开。

1. 选择 **[!UICONTROL Adobe Experience Platform]** 下的选项 **[!UICONTROL Type of audience]**，然后添加所需的受众。

   ![](assets/aep_wkf_readaudience.png)

1. （可选）选择受众后，您可以单击眼睛按钮以查看和/或编辑区段定义（确保再次保存更改）。

   单击眼睛按钮只会将您定向到与Campaign中的选定受众关联的区段生成器（在另一个选项卡中）。

1. 选择 **[!UICONTROL Platform data mapping]** 元素，为选定的Adobe Experience Platform受众指定所需的定向维度。

   默认情况下，用于协调的主键（例如，配置文件表的iRecipientID、应用程序订阅表的iAppSubscriptionID）将自动从下拉列表中可用。 要在主键之外定位，您必须创建一个自定义 **命名空间**.

   >[!NOTE]
   >
   >对于主键之外的目标，还必须创建与自定义命名空间对应的自定义目标映射。 有关目标映射的详细信息，请参阅 [本节](../../administration/using/target-mappings-in-campaign.md).

   ![](assets/aep_wkf_readaudience_namespace.png)

   此列表包含已在实例上配置的所有Experience Data Model (XDM)映射。 有关Adobe Experience Platform数据连接器的更多信息，请参阅 [此专用文档](../../integrating/using/aep-about-data-connector.md).

   ![](assets/aep_wkf_readaudience_namespace2.png)

1. 正确配置受众和定向维度后，单击 **[!UICONTROL Confirm]** 按钮以保存更改。

您现在可以使用其他活动配置工作流。 例如，您可以关联 **[!UICONTROL Email delivery]** 活动，向选定的受众发送电子邮件。

![](assets/aep_wkf_email.png)

>[!NOTE]
>
>通过Campaign Standard，您可以定位所有投放渠道中的Adobe Experience Platform受众：电子邮件、短信、直邮消息、推送通知和应用程序内消息。
>
>*注意：对于所有推送和应用程序内消息，Campaign Standard仅支持投放已知用户档案。

有关如何使用工作流和投放的更多信息，请参阅以下章节：

* [了解工作流](../../automating/using/get-started-workflows.md)
* [构建工作流](../../automating/using/building-a-workflow.md)
* [了解通信渠道](../../channels/using/get-started-communication-channels.md)
* [关于渠道活动](../../automating/using/about-channel-activities.md)
