---
title: 使用 Adobe Experience Platform 属性个性化营销活动
description: 了解如何使用Adobe体验平台属性个性化您的营销活动。
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 4d4e7e58-e161-4e5a-898a-b5c29ffb20e0
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 8%

---

# 使用 Adobe Experience Platform 属性个性化营销活动 {#personalizing-campaigns-using-aep-attributes}

>[!IMPORTANT]
>
>Audience Destinations服务目前处于测试阶段，可能会频繁更新，恕不另行通知。 需要在Azure上托管客户（目前仅适用于北美地区的测试版）才能访问这些功能。 如果您希望访问，请联系Adobe客户关怀团队。
>
>**推送** 和 **应用程序内** 尚无法使用Adobe Experience Platform中的上下文数据进行个性化。

使用 [Adobe Experience Platform受众](../../integrating/using/aep-about-audience-destinations-service.md)，则可以使用体验数据模型(XDM)中仅存在的用户档案属性来个性化消息。

要实现此目的，您必须将这些属性添加到 **[!UICONTROL Read audience]** 活动：

1. 打开 **[!UICONTROL Read audience]** 活动。 在 **[!UICONTROL Additional data]** ，单击 **[!UICONTROL Create element]** 按钮。

   请注意， **[!UICONTROL Additional data]** 选项卡仅在选择Adobe Experience Platform受众后才可用。

   ![](assets/aep_wkf_readaudience_attributes.png)

   >[!NOTE]
   >
   >此功能不支持数组和映射数据类型。 此外，只有来自并集架构的数据才会显示在选取器中。

1. 从列表中选择所需的XDM字段，然后单击 **[!UICONTROL Confirm]**.

   ![](assets/aep_wkf_readaudience_perso1.png)

1. 单击 **[!UICONTROL Add]** 按钮以将其添加到附加数据列表。

   ![](assets/aep_wkf_readaudience_perso3.png)

1. 对要添加到工作流中的每个XDM字段重复这些步骤。

   >[!NOTE]
   >
   >在 **[!UICONTROL Read audience]** 活动。

1. 添加所有字段后，单击 **[!UICONTROL Confirm]** 按钮以保存更改。 现在，即可使用这些配置文件对投放进行个性化。

有关如何创建和个性化投放的更多信息，请参阅Campaign Standard文档：

* [了解通信渠道](../../channels/using/get-started-communication-channels.md)
* [关于渠道活动](../../automating/using/about-channel-activities.md)
* [个性化投放](../../designing/using/personalization.md)
