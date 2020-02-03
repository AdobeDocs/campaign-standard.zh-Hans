---
title: 使用Adobe Experience Platform属性个性化营销活动
description: 了解如何使用Adobe Experience Platform属性个性化您的营销活动。
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
source-git-commit: 2086bbb6fa87106692b3f3744c40ecf40e66caf3

---


# 使用Adobe Experience Platform属性个性化营销活动 {#personalizing-campaigns-using-aep-attributes}

>[!IMPORTANT]
>
>受众目标服务目前处于测试阶段，可能会在不另行通知的情况下频繁进行更新。 客户必须托管在Azure上（目前仅针对北美）才能访问这些功能。 如果您希望访问，请联系Adobe客户关怀。
>
>**推送和** 应用程序内渠道尚不可用 **** ，无法使用Adobe Experience Platform中的情境数据进行个性化。

使用 [Adobe Experience Platform受众配置工作流后](../../audiences/using/aep-about-audience-destinations-service.md)，您可以使用Experience Data Model(XDM)中独有的配置文件属性个性化消息。

为此，您必须在活动中添加以下属 **[!UICONTROL Read audience]**性：

1. 打开活 **[!UICONTROL Read audience]**动。 在选项**[!UICONTROL Additional data]** 卡中，单击按 **[!UICONTROL Create element]**钮。

   >[!NOTE]
   >
   >该选 **[!UICONTROL Additional data]**项卡仅在选择Adobe Experience platform受众后才可用。

   ![](assets/aep_wkf_readaudience_attributes.png)

1. 从列表中选择所需的XDM字段，然后单击 **[!UICONTROL Confirm]**。

   ![](assets/aep_wkf_readaudience_perso1.png)

1. 单击 **[!UICONTROL Add]**按钮可将其添加到其他数据列表。

   ![](assets/aep_wkf_readaudience_perso3.png)

1. 对要添加到工作流中的每个XDM字段重复这些步骤。

   >[!NOTE]
   >
   >在活动中最多可添加20个XDM字 **[!UICONTROL Read audience]**段。

1. 添加所有字段后，单击 **[!UICONTROL Confirm]**按钮以保存更改。 现在，您可以使用它们个性化您的交付。

有关如何创建和个性化分发的详细信息，请参阅Campaign standard文档：

* [了解通信渠道](../../channels/using/discovering-communication-channels.md)
* [关于渠道活动](../../automating/using/about-channel-activities.md)
* [个性化交付](../../designing/using/personalization.md)
