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
source-git-commit: 782a5f89b0361f1cbe59c9b353ca90dec90c3906

---


# 创建多语言推送通知{#creating-a-multilingual-push-notification}

## 关于多语言推送通知 {#about-multilingual-push-notification}

根据用户首选语言和区域发送消息，个性化推送通知内容。您可以在内容编辑器中直接导入多语言推送通知内容变体，并在单一交付中发送多语言推送通知。

此功能根据用于推送通知的交付模板，利用在收件人的配置文件或移动应用程序用户的系统语言首选项中指定的首选语言。如果未为特定用户填充语言首选项，系统将使用在创建多语言推送通知时定义的默认变体。有关如何管理个人资料和订阅者的更多信息，请参阅本 [指南](../../audiences/using/about-profiles-and-audiences.md)。

![](assets/multivariant_push_1.png)

要将多语言内容变体用于推送通知交付，请执行以下步骤：

* [步骤1：上传多语言内容变体](../../channels/using/creating-a-multilingual-push-notification.md#step-1--upload-multilingual-content-variant)
* [步骤2：使用多语言内容变体预览和完成推送通知](../../channels/using/creating-a-multilingual-push-notification.md#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants)
* [步骤3：发送和分析多语言推送通知交付](../../channels/using/creating-a-multilingual-push-notification.md#step-3--send-and-analyze-multilingual-push-notification-delivery)

## 步骤1：上传多语言内容变体 {#step-1--upload-multilingual-content-variant}

在个性化多语言推送通知之前，我们首先需要在多语言交付模板中上传内容变体并创建交付。

>[!NOTE]
>
>如果要为每个语言变体手动创建变体，您也可以跳过此步骤。

1. 在中 **[!UICONTROL Marketing activities]**，单击 **[!UICONTROL Create]** 按钮，然后选择 **[!UICONTROL Push notification]**。
1. 如果要将订阅了移动应用程序的Adobe **[!UICONTROL Send multilingual push to Campaign profiles]** Campaign配置文件或模板 **[!UICONTROL Send multilingual push to app subscriber]** 定向到已选择接收移动应用程序通知的所有用户，请选择模板。

   ![](assets/multivariant_push_2.png)

1. 输入推送通知属性，并在 **[!UICONTROL Associate a Mobile App to a delivery]** 字段中选择移动应用程序。

   请注意，下拉菜单将显示SDK V和Adobe Experience Platform SDK应用程序。

1. **[!UICONTROL Audiences]** 在窗口中，拖放查询以微调受众。

   添加的查询取决于所选的模板：如果您选择 **[!UICONTROL Send multilingual push to Campaign profiles]** 了模板，则可以查询移动应用程序的已知收件人。但是，如果您选择 **[!UICONTROL Send multilingual push to app subscriber]** 了模板，则可以查询已选择加入某个特定应用程序的所有用户。

   ![](assets/push_notif_audience.png)

1. 在 **[!UICONTROL Manage Content Variants]** 窗口中，拖放您的文件或从计算机中选择一个文件。

   该文件必须采用UTF编码，并且必须具有一个特定布局，单击 **[!UICONTROL Download the sample file]** 该选项即可找到它。您还应对区域设置值使用适当的语法。有关文件格式和支持的区域设置的详细信息，请参阅此 [技术说明](http://helpx.adobe.com/campaign/kb/acs-generate-csv-multilingual-push.html)。

   ![](assets/multivariant_push_4.png)

1. 上传文件后，语言变体会自动填充 **[!UICONTROL Variants]** 到选项卡中。请注意，如果目标用户没有指定首选语言，则可以在文件 **[!UICONTROL Default variant]** 中提供您的默认内容变体。

   ![](assets/multivariant_push_5.png)

1. **[!UICONTROL Variant selection]** 选项卡将提供一个脚本，用于根据交付模板确定要考虑的语言首选项。这是一个现成的脚本，无需您进行任何更改。
1. 如果要添加导入文件中不存在的更多变体，则可以单击 **[!UICONTROL Add an element]** 该按钮，并根据需要添加任意数量的新语言变体。

   通过添加从文件上传的变体以外的变体，任何内容都不会链接到此语言。您必须在交付功能板中直接编辑内容。

   ![](assets/multivariant_push_6.png)

1. 完成 **[!UICONTROL Create]** 配置后单击。您始终可以返回 **[!UICONTROL Content variant]** 窗口，并从传送仪表板进行一些更改。

   ![](assets/multivariant_push_8.png)

您现在可以开始个性化多语言推送通知。

## 步骤2：使用多语言内容变体预览和完成推送通知 {#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants}

上传包含内容变体的文件后，您现在可以从推送通知交付中预览不同变体。

除了从文件上传的变体之外，还可以创建和编辑更多变体。

1. **[!UICONTROL Content]** 在传送功能板窗口中，下拉菜单允许您根据所选语言预览推送通知内容。

   ![](assets/multivariant_push_7.png)

1. 如果未为特定语言指定内容变体，请单击预览下方的铃图标以开始向此语言变体添加内容。

   通过单击 **[!UICONTROL Content]** 窗口，推送通知表示下拉列表中所选语言的内容。在此窗口中所做的更改只会影响一种语言。

1. 您还可以单击内容变体以进一步自定义示例字段，例如个性化字段。

   有关如何自定义推送通知的更多信息，请参阅本 [节](../../channels/using/customizing-a-push-notification.md)。

   ![](assets/multivariant_push_9.png)

1. 如果要添加或删除语言变体，请单击 **[!UICONTROL Content variant]** 该窗口。

   请注意，添加新语言后，您必须手动向链接到添加的语言的推送通知中添加内容。

   ![](assets/multivariant_push_10.png)

您的多语言推送通知交付现已准备好发送。

## 步骤3：发送和分析多语言推送通知交付 {#step-3--send-and-analyze-multilingual-push-notification-delivery}

您的多语言内容变体推送通知现已准备好发送给您的用户。

1. 要开始准备发送，请单击 **[!UICONTROL Prepare]** 按钮。
1. 准备完成后，您可以单击 **[!UICONTROL Confirm]** 按钮以开始发送多语言推送。

   ![](assets/multivariant_push_12.png)

1. 成功发送推送通知后，单击 **[!UICONTROL Reports]** 该图标， **[!UICONTROL Dynamic reports]** 分析交付成功与否。

   ![](assets/multivariant_push_13.png)

1. 选择 **[!UICONTROL Push notification report]**。
1. 将 **[!UICONTROL Variant]** 维度拖放到面板中，开始筛选数据。

   ![](assets/multivariant_push_11.png)

您现在可以衡量您的多语言推送通知交付对收件人的影响。

**相关主题：**

* [推送通知报告](../../reporting/using/push-notification-report.md)
* [在工作流中发送推送通知](../../automating/using/push-notification-delivery.md)
* [使用一个工作流程接触多语言受众](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)
