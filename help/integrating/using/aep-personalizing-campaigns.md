---
solution: Campaign Standard
product: campaign
title: 使用 Adobe Experience Platform 属性个性化营销策划
description: 了解如何使用Adobe Experience Platform属性个性化您的活动。
audience: automating
content-type: reference
topic-tags: channel-activities
translation-type: tm+mt
source-git-commit: 35d61efce8d752ea30b7eaad55e6c23d4debd853
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 8%

---


# 使用 Adobe Experience Platform 属性个性化营销策划 {#personalizing-campaigns-using-aep-attributes}

>[!IMPORTANT]
>
>受众目标服务目前处于测试阶段，可能会在不通知的情况下频繁进行更新。 客户需要托管在Azure上（目前仅针对北美）才能访问这些功能。 如果您希望访问，请联系Adobe客户关怀团队。
>
>**Pushand** In- **Appchannel尚不** 可使用Adobe Experience Platform中的情境数据进行个性化。

使用[Adobe Experience Platform 受众](../../integrating/using/aep-about-audience-destinations-service.md)配置工作流后，您便可以使用“体验模型”(XDM)中独有的用户档案属性个性化消息。

为此，必须将以下属性添加到&#x200B;**[!UICONTROL Read audience]**&#x200B;活动:

1. 打开&#x200B;**[!UICONTROL Read audience]**&#x200B;活动。 在&#x200B;**[!UICONTROL Additional data]**&#x200B;选项卡中，单击&#x200B;**[!UICONTROL Create element]**&#x200B;按钮。

   请注意，**[!UICONTROL Additional data]**&#x200B;选项卡仅在选择Adobe Experience Platform受众后才可用。

   ![](assets/aep_wkf_readaudience_attributes.png)

   >[!NOTE]
   >
   >此功能不支持数组和映射数据类型。 此外，拾色器中将仅显示来自合并模式的数据。

1. 从列表中选择所需的XDM字段，然后单击&#x200B;**[!UICONTROL Confirm]**。

   ![](assets/aep_wkf_readaudience_perso1.png)

1. 单击&#x200B;**[!UICONTROL Add]**&#x200B;按钮，将其添加到其他列表。

   ![](assets/aep_wkf_readaudience_perso3.png)

1. 对要添加到工作流中的每个XDM字段重复这些步骤。

   >[!NOTE]
   >
   >在&#x200B;**[!UICONTROL Read audience]**&#x200B;活动中最多可添加20个XDM字段。

1. 添加所有字段后，单击&#x200B;**[!UICONTROL Confirm]**&#x200B;按钮以保存更改。 现在，您可以使用它们来个性化您的投放。

有关如何创建和个性化投放的详细信息，请参阅Campaign Standard文档：

* [了解通信渠道](../../channels/using/get-started-communication-channels.md)
* [关于渠道活动](../../automating/using/about-channel-activities.md)
* [个性化投放](../../designing/using/personalization.md)
