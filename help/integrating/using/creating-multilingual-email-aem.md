---
solution: Campaign Standard
product: campaign
title: 通过 Adobe Experience Manager 集成创建多语言电子邮件.
description: 借助Adobe Experience Manager集成，您可以直接在AEM中创建内容，然后在Adobe Campaign中使用。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: 触发器
role: 数据架构师
level: 中间
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 5%

---


# 通过 Adobe Experience Manager 集成创建多语言电子邮件 {#creating-multilingual-email-aem}

使用此文档，您将学习如何使用Adobe Experience Manager内容和语言副本创建多语言电子邮件。

先决条件包括：

* 访问为集成配置的AEM实例。
* 访问为集成配置的Adobe Campaign实例。
* Adobe Campaign多语言电子邮件模板，配置为接收AEM内容。

## 在Adobe Experience Manager {#creating-email-content-aem}中创建新电子邮件内容

1. 从Adobe Experience Manager主页，选择&#x200B;**[!UICONTROL Site]**。

   ![](assets/aem_acs_1.png)

1. 选择要在其中创建页面的文件夹，然后单击&#x200B;**[!UICONTROL Create]**，然后单击&#x200B;**[!UICONTROL Page]**。 在此，我们将在en_us文件夹中创建我们的页面，该文件夹将是我们的默认语言。

   ![](assets/aem_acs_2.png)

1. 选择&#x200B;**[!UICONTROL Adobe Campaign Email (ACS)]**&#x200B;模板。

1. 填写电子邮件的属性，然后单击&#x200B;**[!UICONTROL Create]**。

   ![](assets/aem_acs_3.png)

1. 打开新的电子邮件内容并根据需要进行个性化设置。 有关详细信息，请参见此 [ 页面](../../integrating/using/creating-email-experience-manager.md#editing-email-aem)。

   ![](assets/aem_acs_4.png)

1. 从&#x200B;**[!UICONTROL Workflow]**&#x200B;选项卡中，选择&#x200B;**[!UICONTROL Approve for Adobe Campaign]**&#x200B;验证工作流。 如果电子邮件使用的内容未经批准，您将无法以Adobe Campaign发送。

   ![](assets/aem_acs_7.png)

1. 单击&#x200B;**[!UICONTROL Complete work item]**&#x200B;窗口中的&#x200B;**[!UICONTROL Complete]**，然后单击&#x200B;**[!UICONTROL Newsletter review]**。

1. 单击 **[!UICONTROL Complete]**，然后单击 **[!UICONTROL Newsletter approval]**。定义内容和发送参数后，您可以继续在Adobe Campaign Standard中批准、准备和发送电子邮件。

   ![](assets/aem_acs_8.png)

## 创建语言副本{#creating-language-copies}

设计电子邮件内容后，您现在需要创建语言副本，这些副本将作为变体与Adobe Campaign Standard同步。

1. 选择之前创建的页面，单击&#x200B;**[!UICONTROL Create]**，然后单击&#x200B;**[!UICONTROL Language Copy]**。

   ![](assets/aem_acs_5.png)

1. 选择您之前创建的电子邮件内容，这些内容将以所选语言翻译，然后单击&#x200B;**[!UICONTROL Next]**。

   ![](assets/aem_acs_6.png)

1. 在&#x200B;**[!UICONTROL Target language(s)]**&#x200B;下拉列表中，选择内容的翻译语言，然后单击&#x200B;**[!UICONTROL Next]**。

   ![](assets/aem_acs_9.png)

1. 单击 **[!UICONTROL Create]**.

您的语言副本现已创建，您现在可以根据所选语言编辑您的内容。

>[!CAUTION]
>
>每个语言副本都需要通过&#x200B;**[!UICONTROL Approve for Adobe Campaign]**&#x200B;验证工作流批准。 如果电子邮件使用的内容未经批准，您将无法以Adobe Campaign发送。

![](assets/aem_acs_11.png)

## 在Adobe Campaign Standard{#multilingual-acs}中创建多语言内容

1. 从Adobe Campaign Standard主页，单击&#x200B;**[!UICONTROL Create an email]**。

   ![](assets/aem_acs_12.png)

1. 选择配置为接收Adobe Experience Manager内容的Adobe Campaign多语言电子邮件模板。 要了解有关如何创建链接到您的Adobe Experience Manager实例的模板的更多信息，请参阅此[页面](../../integrating/using/configure-experience-manager.md#config-acs)。

   >[!NOTE]
   >
   >在这种情况下，您需要重复内置模板&#x200B;**[!UICONTROL Multilingual email (mailMultiLang)]**&#x200B;才能发送多语言电子邮件。

   ![](assets/aem_acs_13.png)

1. 填写电子邮件的&#x200B;**[!UICONTROL Properties]**&#x200B;和&#x200B;**[!UICONTROL Audience]**，然后单击&#x200B;**[!UICONTROL Create]**。

1. 在&#x200B;**[!UICONTROL Edit properties]**&#x200B;中，确保在&#x200B;**[!UICONTROL Content]**&#x200B;下拉列表中正确设置了您的Adobe Experience Manager帐户。

   ![](assets/aem_acs_20.png)

1. 单击 **[!UICONTROL Language copy creation]**.

   ![](assets/aem_acs_16.png)

1. 选择您之前创建的Adobe Experience Manager内容，然后单击&#x200B;**[!UICONTROL Confirm]**。 此处显示的Adobe Experience Manager内容只是已验证的内容，可在其&#x200B;**[!UICONTROL Label]**&#x200B;和&#x200B;**[!UICONTROL Path]**&#x200B;上过滤。

   >[!NOTE]
   >
   >所选语言副本将设置为默认值，您以后可以在&#x200B;**[!UICONTROL Content variant]**&#x200B;块中更改它。

   ![](assets/aem_acs_17.png)

1. 单击&#x200B;**[!UICONTROL Create variants]**&#x200B;链接您的多语言内容。 Adobe Campaign Standard随后将自动将其他语言副本链接到此内容。 创建的变体与在Adobe Experience Manager中选择的变体具有相同的标签和代码语言。

   ![](assets/aem_acs_18.png)

1. 如果需要，单击&#x200B;**[!UICONTROL Content variant]**&#x200B;块以更改默认变体，然后单击&#x200B;**[!UICONTROL Confirm]**。

   ![](assets/aem_acs_19.png)

1. 如果您的内容或变体在Adobe Experience Manager中进行了更新，则可以在Adobe Campaign Standard中直接使用&#x200B;**[!UICONTROL Refresh AEM contents]**&#x200B;按钮来同步它。

1. 您的电子邮件现已准备好发送。 有关此的详细信息，请参阅此[页](../../sending/using/get-started-sending-messages.md)。

您的受众将根据其&#x200B;**[!UICONTROL Profiles]**&#x200B;中设置的&#x200B;**[!UICONTROL Preferred languages]**&#x200B;接收您的电子邮件。 要了解有关如何编辑用户档案和首选语言的更多信息，请参阅此[页面](../../audiences/using/editing-profiles.md)。
