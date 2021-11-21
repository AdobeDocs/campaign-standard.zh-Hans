---
title: 通过 Adobe Experience Manager 集成创建多语言电子邮件.
description: 通过Adobe Experience Manager集成，您可以直接在AEM中创建内容，稍后在Adobe Campaign中使用它。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 0f66fe2b-22b1-49d7-a080-29b00941a2cc
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 5%

---

# 通过 Adobe Experience Manager 集成创建多语言电子邮件 {#creating-multilingual-email-aem}

使用本文档，您将了解如何使用Adobe Experience Manager内容和语言副本创建多语言电子邮件。

先决条件包括：

* 访问为集成配置的AEM实例。
* 访问为集成配置的Adobe Campaign实例。
* 配置为接收AEM内容的Adobe Campaign多语言电子邮件模板。

## 在Adobe Experience Manager中创建新电子邮件内容 {#creating-email-content-aem}

1. 从Adobe Experience Manager主页中，选择 **[!UICONTROL Site]**.

   ![](assets/aem_acs_1.png)

1. 选择要在其中创建页面的文件夹，然后单击 **[!UICONTROL Create]** then **[!UICONTROL Page]**. 在本例中，我们在en_us文件夹中创建页面，该文件夹将作为我们的默认语言。

   ![](assets/aem_acs_2.png)

1. 选择 **[!UICONTROL Adobe Campaign Email (ACS)]** 模板。

1. 填写电子邮件的属性并单击 **[!UICONTROL Create]**.

   ![](assets/aem_acs_3.png)

1. 打开您的新电子邮件内容并根据需要对其进行个性化。 有关详细信息，请参见此 [ 页面](../../integrating/using/creating-email-experience-manager.md#editing-email-aem)。

   ![](assets/aem_acs_4.png)

1. 从 **[!UICONTROL Workflow]** 选项卡，选择 **[!UICONTROL Approve for Adobe Campaign]** 验证工作流。 如果电子邮件使用的内容未获得批准，则将无法在Adobe Campaign中发送电子邮件。

   ![](assets/aem_acs_7.png)

1. 单击 **[!UICONTROL Complete]** then **[!UICONTROL Newsletter review]** 从 **[!UICONTROL Complete work item]** 窗口。

1. 单击 **[!UICONTROL Complete]**，然后单击 **[!UICONTROL Newsletter approval]**。定义内容和发送参数后，您可以继续在Adobe Campaign Standard中批准、准备和发送电子邮件。

   ![](assets/aem_acs_8.png)

## 创建语言副本 {#creating-language-copies}

设计电子邮件内容后，您现在需要创建语言副本，该副本将作为变体与Adobe Campaign Standard同步。

1. 选择您之前创建的页面，单击 **[!UICONTROL Create]** then **[!UICONTROL Language Copy]**.

   ![](assets/aem_acs_5.png)

1. 选择您之前创建的电子邮件内容，这些内容将以所选语言进行翻译，然后单击 **[!UICONTROL Next]**.

   ![](assets/aem_acs_6.png)

1. 在 **[!UICONTROL Target language(s)]** 下拉列表中，选择内容的翻译语言，然后单击 **[!UICONTROL Next]**.

   ![](assets/aem_acs_9.png)

1. 单击 **[!UICONTROL Create]**。

现在，您已创建语言副本，您现在可以根据所选的语言编辑内容。

>[!CAUTION]
>
>每个语言副本都需要通过 **[!UICONTROL Approve for Adobe Campaign]** 验证工作流。 如果电子邮件使用的内容未获得批准，则将无法在Adobe Campaign中发送电子邮件。

![](assets/aem_acs_11.png)

## 在Adobe Campaign Standard中创建多语言内容 {#multilingual-acs}

1. 从Adobe Campaign Standard主页，单击 **[!UICONTROL Create an email]**.

   ![](assets/aem_acs_12.png)

1. 选择配置为接收Adobe Campaign内容的Adobe Experience Manager多语言电子邮件模板。 要了解有关如何创建链接到Adobe Experience Manager实例的模板的更多信息，请参阅此 [页面](../../integrating/using/configure-experience-manager.md#config-acs).

   >[!NOTE]
   >
   >在这种情况下，您需要复制内置模板 **[!UICONTROL Multilingual email (mailMultiLang)]** 以发送您的多语言电子邮件。

   ![](assets/aem_acs_13.png)

1. 填写 **[!UICONTROL Properties]** 和 **[!UICONTROL Audience]** ，单击 **[!UICONTROL Create]**.

1. 在 **[!UICONTROL Edit properties]**，请确保在中正确设置您的Adobe Experience Manager帐户 **[!UICONTROL Content]** 下拉菜单。

   ![](assets/aem_acs_20.png)

1. 单击 **[!UICONTROL Language copy creation]**。

   ![](assets/aem_acs_16.png)

1. 选择您之前创建的Adobe Experience Manager内容，然后单击 **[!UICONTROL Confirm]**. 此处显示的Adobe Experience Manager内容只是已验证的内容，并可对其进行过滤 **[!UICONTROL Label]** 和 **[!UICONTROL Path]**.

   >[!NOTE]
   >
   >所选语言副本将设置为默认副本，您以后可以在 **[!UICONTROL Content variant]** 块。

   ![](assets/aem_acs_17.png)

1. 单击 **[!UICONTROL Create variants]** 链接多语言内容。 然后，Adobe Campaign Standard会自动将其他语言副本链接到此内容。 创建的变体将具有与在Adobe Experience Manager中选择的变体相同的标签和代码语言。

   ![](assets/aem_acs_18.png)

1. 单击 **[!UICONTROL Content variant]** 阻止更改默认变体（如果需要）并单击 **[!UICONTROL Confirm]**.

   ![](assets/aem_acs_19.png)

1. 如果您的内容或变体在Adobe Experience Manager中进行了更新，则可以在Adobe Campaign Standard中直接将其与 **[!UICONTROL Refresh AEM contents]** 按钮。

1. 您的电子邮件现已准备就绪，可供发送。 有关此内容的更多信息，请参阅此内容 [页面](../../sending/using/get-started-sending-messages.md).

   >[!NOTE]
   >
   >如果电子邮件使用的是未经批准的AEM内容，则无法在Adobe Campaign中发送电子邮件。

受众将收到您的电子邮件，具体取决于 **[!UICONTROL Preferred languages]** 设置 **[!UICONTROL Profiles]**. 要详细了解如何编辑用户档案和首选语言，请参阅 [页面](../../audiences/using/editing-profiles.md).
