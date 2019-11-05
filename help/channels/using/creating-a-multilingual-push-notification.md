---
title: 创建多语言推送通知
description: 创建多语种推送通知，以用户的首选语言和区域为目标。
page-status-flag: 从未激活
uuid: d4aff741-e969-47c6-bae8-787c6c673191
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 频道
content-type: 参考
topic-tags: 推送通知
discoiquuid: f9bb2235-d388-4025-9ace-734beb0c1961
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 创建多语言推送通知{#creating-a-multilingual-push-notification}

## 关于多语言推送通知 {#about-multilingual-push-notification}

根据用户喜欢的语言和区域发送消息，个性化推送通知内容。 您可以直接在内容编辑器中导入多语言推送通知内容变体，并通过单次分发发送多语言推送通知。

此功能根据用于推送通知的交付模板，利用在收件人配置文件中指定的首选语言或移动应用程序订阅者的系统语言首选项。 如果未为特定用户填充语言首选项，则系统将使用创建多语言推送通知时定义的默认变体。 有关如何管理您的配置文件和订阅者的详细信息，请参阅本 [指南](../../audiences/using/about-profiles-and-audiences.md)。

![](assets/multivariant_push_1.png)

要将多语言内容变体用于推送通知交付，请执行以下步骤：

* [第1步：上传多语言内容变体](#step-1--upload-multilingual-content-variant)
* [第2步：使用多语言内容变体预览并最终确定推送通知](#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants)
* [第3步：发送和分析多语言推送通知交付](#step-3--send-and-analyze-multilingual-push-notification-delivery)

## 第1步：上传多语言内容变体 {#step-1--upload-multilingual-content-variant}

在个性化您的多语言推送通知之前，我们首先需要在多语言交付模板中上传内容变体并创建交付。

>[!NOTE]
>
>如果要为每个语言变体手动创建变体，则还可以跳过此步骤。

1. 在中，单 **[!UICONTROL Marketing activities]**&#x200B;击按钮，然 **[!UICONTROL Create]** 后选择 **[!UICONTROL Push notification]**。
1. 如果要定 **[!UICONTROL Send multilingual push to Campaign profiles]****[!UICONTROL Send multilingual push to app subscriber]** 位订阅了移动应用程序的Adobe Campaign配置文件或模板，则选择该模板，以向已选择接收移动应用程序通知的所有用户发送推送通知。

   ![](assets/multivariant_push_2.png)

1. 输入您的推送通知属性，然后在字段中选择您的移动应用 **[!UICONTROL Associate a Mobile App to a delivery]** 程序。

   请注意，下拉列表将同时显示SDK V4和Adobe Experience Platform SDK应用程序。

1. 在窗口 **[!UICONTROL Audiences]** 中，拖放查询以优化您的受众。

   添加的查询取决于所选的模板：如果选择了模 **[!UICONTROL Send multilingual push to Campaign profiles]** 板，则可以查询移动应用程序的已知收件人。 但是，如果您选择 **[!UICONTROL Send multilingual push to app subscriber]** 了模板，则可以查询已选择某个特定应用程序的所有订阅者。
   >[!NOTE]
   >
   >如果您以特定语言为目标受众，则需要在CSV文件中列出每种目标语言。

   ![](assets/push_notif_audience.png)

1. 在窗口 **[!UICONTROL Manage Content Variants]** 中，拖放文件或从计算机中选择文件。

   文件必须采用UTF8编码，并且必须具有特定布局，可通过单击选项找到该布 **[!UICONTROL Download the sample file]** 局。 您还应该为区域设置值使用正确的语法。 有关文件格式和支持的区域设置的详细信息，请参阅此技 [术说明](http://helpx.adobe.com/campaign/kb/acs-generate-csv-multilingual-push.html)。

   ![](assets/multivariant_push_4.png)

1. 上传文件后，语言变体将自动填充在选项卡 **[!UICONTROL Variants]** 中。 请注意，如果未为目标用 **[!UICONTROL Default variant]** 户指定首选语言，则您可以在文件中提供默认内容变体。

   ![](assets/multivariant_push_5.png)

1. 该选 **[!UICONTROL Variant selection]** 项卡将提供一个脚本，以根据交付模板确定要考虑的语言首选项。 这是一个现成的脚本，不需要您进行任何更改。
1. 如果要添加导入的文件中不存在的更多变体，可以通过单击按钮来添加，并根 **[!UICONTROL Add an element]** 据需要添加任意数量的新语言变体。

   通过添加从文件上载的变体以外的变体，不会将任何内容链接到此语言。 您必须直接在分发功能板中编辑内容。

   ![](assets/multivariant_push_6.png)

1. 完 **[!UICONTROL Create]** 成配置后单击。 您始终可以返回窗口， **[!UICONTROL Content variant]** 并从交付功能板中进行一些更改。

   ![](assets/multivariant_push_8.png)

您现在可以开始个性化多语言推送通知。

## 第2步：使用多语言内容变体预览并最终确定推送通知 {#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants}

在上传包含内容变体的文件后，您现在可以从推送通知交付中预览不同的变体。

除了从文件上载的变体之外，还可以创建和编辑更多变体。

1. 在分 **[!UICONTROL Content]** 发功能板的窗口中，下拉菜单允许您根据所选的语言预览推送通知内容。

   ![](assets/multivariant_push_7.png)

1. 如果未为特定语言指定内容变体，请单击预览下方的铃图标，开始向此语言变体添加内容。

   通过单击 **[!UICONTROL Content]** 窗口，推送通知表示来自下拉列表中所选语言的内容。 在此窗口中所做的更改只会影响一种语言。

1. 您还可以单击内容变体以进一步自定义它，例如使用个性化字段。

   有关如何自定义推送通知的详细信息，请参阅此 [部分](../../channels/using/customizing-a-push-notification.md)。

   ![](assets/multivariant_push_9.png)

1. 如果要 **[!UICONTROL Content variant]** 添加或删除语言变体，请单击窗口。

   请注意，通过添加新语言，您必须手动将内容添加到链接到所添加语言的推送通知中。

   ![](assets/multivariant_push_10.png)

您的多语言推送通知交付现已准备就绪。

## 第3步：发送和分析多语言推送通知交付 {#step-3--send-and-analyze-multilingual-push-notification-delivery}

您的多语言内容变体推送通知现已准备好发送给您的用户。

1. 要开始准备发送，请单击该 **[!UICONTROL Prepare]** 按钮。
1. 当准备完成时，无需发出任何警告，您可以单 **[!UICONTROL Confirm]** 击按钮开始发送多语言推送。

   ![](assets/multivariant_push_12.png)

1. 成功发送推送通知后，单击 **[!UICONTROL Reports]** 图标，然 **[!UICONTROL Dynamic reports]** 后分析交付的成功。

   ![](assets/multivariant_push_13.png)

1. Select **[!UICONTROL Push notification report]**.
1. 将维度拖放 **[!UICONTROL Variant]** 到面板以开始筛选数据。

   ![](assets/multivariant_push_11.png)

您现在可以衡量多语言推送通知交付对收件人的影响。

**相关主题：**

* [推送通知报告](../../reporting/using/push-notification-report.md)
* [在工作流中发送推送通知](../../automating/using/push-notification-delivery.md)
* [使用一个工作流程触及多语言受众](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)
