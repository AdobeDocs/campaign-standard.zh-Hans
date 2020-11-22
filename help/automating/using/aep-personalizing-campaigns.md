---
solution: Campaign Standard
product: campaign
title: 使用 Adobe Experience Platform 属性个性化营销策划
description: 了解如何使用活动体验平台属性来个性化您的Adobe。
audience: automating
content-type: reference
topic-tags: channel-activities
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 8%

---


# 使用 Adobe Experience Platform 属性个性化营销策划 {#personalizing-campaigns-using-aep-attributes}

>[!IMPORTANT]
>
>受众目标服务目前处于测试阶段，可能会在不通知的情况下频繁进行更新。 客户必须托管在Azure上（目前仅限北美的beta版），才能访问这些功能。 如果您想要访问，请联系Adobe客户服务中心。
>
>**推送** 和应 **用程序内渠道尚不可用** ，无法使用Adobe Experience Platform的情境数据进行个性化。

在您的工作流配置了 [Adobe Experience Platform受众](../../audiences/using/aep-about-audience-destinations-service.md)后，您可以使用体验数据模型(XDM)中独有的用户档案属性来个性化消息。

为此，您必须在活动中添加以下属 **[!UICONTROL Read audience]** 性：

1. 打开 **[!UICONTROL Read audience]** 活动。 In the **[!UICONTROL Additional data]** tab, click the **[!UICONTROL Create element]** button.

   请注意， **[!UICONTROL Additional data]** 只有在选择了Adobe Experience Platform受众后，选项卡才可用。

   ![](assets/aep_wkf_readaudience_attributes.png)

   >[!NOTE]
   >
   >此功能不支持数组和映射数据类型。 此外，只有合并模式中的数据才会显示在选取器中。

1. 从列表中选择所需的XDM字段，然后单击 **[!UICONTROL Confirm]**。

   ![](assets/aep_wkf_readaudience_perso1.png)

1. 单击按 **[!UICONTROL Add]** 钮，将其添加到其他列表。

   ![](assets/aep_wkf_readaudience_perso3.png)

1. 对要添加到工作流中的每个XDM字段重复这些步骤。

   >[!NOTE]
   >
   >在活动中最多可添加20个XDM字 **[!UICONTROL Read audience]** 段。

1. 添加所有字段后，单击按 **[!UICONTROL Confirm]** 钮以保存更改。 现在，您可以使用它们来个性化您的投放。

有关如何创建和个性化投放的更多信息，请参阅Campaign Standard文档：

* [了解通信渠道](../../channels/using/get-started-communication-channels.md)
* [关于渠道活动](../../automating/using/about-channel-activities.md)
* [个性化投放](../../designing/using/personalization.md)
