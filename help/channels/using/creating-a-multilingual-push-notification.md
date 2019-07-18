---
title: 创建多语言推送通知
seo-title: 创建多语言推送通知
description: 创建多语言推送通知
seo-description: 创建多语言推送通知，以瞄准用户首选语言和区域。
page-status-flag: 从未激活
uuid: d aff741-e969-47c6-bae8-787c6 c673191
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 频道
content-type: reference
topic-tags: 推送通知
discoiquuid: f9bb2235-d388-4025-9ace-734bb0 c1961
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 6df0e764750a31f29d6fe3ec4d92e19b3f07f728

---


# Creating a multilingual push notification{#creating-a-multilingual-push-notification}

## About multilingual push notification {#about-multilingual-push-notification}

根据用户首选语言和区域发送消息，个性化推送通知内容。您可以在内容编辑器中直接导入多语言推送通知内容变体，并在单一交付中发送多语言推送通知。

此功能根据用于推送通知的交付模板，利用在收件人的配置文件或移动应用程序用户的系统语言首选项中指定的首选语言。如果未为特定用户填充语言首选项，系统将使用在创建多语言推送通知时定义的默认变体。For more information on how to manage your profiles and subscribers, refer to this [guide](../../audiences/using/about-profiles-and-audiences.md).

![](assets/multivariant_push_1.png)

要将多语言内容变体用于推送通知交付，请执行以下步骤：

* [步骤1：上传多语言内容变体](../../channels/using/creating-a-multilingual-push-notification.md#step-1--upload-multilingual-content-variant)
* [步骤2：使用多语言内容变体预览和完成推送通知](../../channels/using/creating-a-multilingual-push-notification.md#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants)
* [步骤3：发送和分析多语言推送通知交付](../../channels/using/creating-a-multilingual-push-notification.md#step-3--send-and-analyze-multilingual-push-notification-delivery)

## Step 1: Upload multilingual content variant {#step-1--upload-multilingual-content-variant}

在个性化多语言推送通知之前，我们首先需要在多语言交付模板中上传内容变体并创建交付。

>[!NOTE]
>
>如果要为每个语言变体手动创建变体，您也可以跳过此步骤。

1. In the **[!UICONTROL Marketing activities]**, click the **[!UICONTROL Create]** button then select **[!UICONTROL Push notification]**.
1. Select the template **[!UICONTROL Send multilingual push to Campaign profiles]** if you want to target the Adobe Campaign profiles who have subscribed to your mobile application or the template **[!UICONTROL Send multilingual push to app subscriber]** to send a push notification to all users who have opted in to receive notifications from your mobile application.

   ![](assets/multivariant_push_2.png)

1. Enter your push notification properties and select your mobile app in the **[!UICONTROL Associate a Mobile App to a delivery]** field.

   请注意，下拉菜单将显示SDK V和Adobe Experience Platform SDK应用程序。

1. **[!UICONTROL Audiences]** 在窗口中，拖放查询以微调受众。

   The queries added depend on the chosen template: if you chose the **[!UICONTROL Send multilingual push to Campaign profiles]** template you can query known recipients of your mobile application. Whereas if you chose the **[!UICONTROL Send multilingual push to app subscriber]** template, you can query all subscribers of a particular app who have opted in.

   ![](assets/push_notif_audience.png)

1. In the **[!UICONTROL Manage Content Variants]** window, drag and drop your file or select a file from your computer.

   The file has to be UTF8 encoded and must have a specific layout which can be found by clicking the **[!UICONTROL Download the sample file]** option. 您还应对区域设置值使用适当的语法。For more information regarding the file format and the supported locales, refer to this [technote](http://helpx.adobe.com/campaign/kb/acs-generate-csv-multilingual-push.html).

   ![](assets/multivariant_push_4.png)

1. After uploading your file, the language variants are automatically populated in the **[!UICONTROL Variants]** tab. Note that you can provide a **[!UICONTROL Default variant]** in the file which will be your default content variant if no preferred language is specified for the targeted user.

   ![](assets/multivariant_push_5.png)

1. **[!UICONTROL Variant selection]** 选项卡将提供一个脚本，用于根据交付模板确定要考虑的语言首选项。这是一个现成的脚本，无需您进行任何更改。
1. If you want to add more variants not present in the imported file, you can do so by clicking the **[!UICONTROL Add an element]** button and add as many new language variants as needed.

   通过添加从文件上传的变体以外的变体，任何内容都不会链接到此语言。您必须在交付功能板中直接编辑内容。

   ![](assets/multivariant_push_6.png)

1. Click **[!UICONTROL Create]** when the configuration is done. You can always come back to the **[!UICONTROL Content variant]** window and make some changes from your delivery dashboard.

   ![](assets/multivariant_push_8.png)

您现在可以开始个性化多语言推送通知。

## Step 2: Preview and finalize a push notification using multilingual content variants {#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants}

上传包含内容变体的文件后，您现在可以从推送通知交付中预览不同变体。

除了从文件上传的变体之外，还可以创建和编辑更多变体。

1. **[!UICONTROL Content]** 在传送功能板窗口中，下拉菜单允许您根据所选语言预览推送通知内容。

   ![](assets/multivariant_push_7.png)

1. 如果未为特定语言指定内容变体，请单击预览下方的铃图标以开始向此语言变体添加内容。

   By clicking the **[!UICONTROL Content]** window, the push notification represents the content from the language selected in the drop down. 在此窗口中所做的更改只会影响一种语言。

1. 您还可以单击内容变体以进一步自定义示例字段，例如个性化字段。

   For more information on how to customize your push notification, refer to this [section](../../channels/using/customizing-a-push-notification.md).

   ![](assets/multivariant_push_9.png)

1. Click the **[!UICONTROL Content variant]** window if you want to add or delete language variants.

   请注意，添加新语言后，您必须手动向链接到添加的语言的推送通知中添加内容。

   ![](assets/multivariant_push_10.png)

您的多语言推送通知交付现已准备好发送。

## Step 3: Send and analyze multilingual push notification delivery {#step-3--send-and-analyze-multilingual-push-notification-delivery}

您的多语言内容变体推送通知现已准备好发送给您的用户。

1. To start preparing the send, click the **[!UICONTROL Prepare]** button.
1. When the preparation is finished with no warnings, you can click the **[!UICONTROL Confirm]** button to start sending your multilingual push.

   ![](assets/multivariant_push_12.png)

1. After successfully sending your push notification, click the **[!UICONTROL Reports]** icon then **[!UICONTROL Dynamic reports]** to analyze the success of your delivery.

   ![](assets/multivariant_push_13.png)

1. Select **[!UICONTROL Push notification report]**.
1. Drag and drop the **[!UICONTROL Variant]** dimension to your panel to start filtering your data.

   ![](assets/multivariant_push_11.png)

您现在可以衡量您的多语言推送通知交付对收件人的影响。

**相关主题：**

* [推送通知报告](../../reporting/using/push-notification-report.md)
* [在工作流中发送推送通知](../../automating/using/push-notification-delivery.md)

