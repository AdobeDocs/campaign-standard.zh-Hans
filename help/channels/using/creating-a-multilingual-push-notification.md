---
solution: Campaign Standard
product: campaign
title: 创建多语言推送通知
description: 创建多语言推送通知以定向使用户首选语言和区域的用户。
audience: channels
content-type: reference
topic-tags: push-notifications
feature: 推送
role: User
level: Intermediate
exl-id: 1b81f6e9-cb31-4664-af78-22e70043fbc8
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '921'
ht-degree: 3%

---

# 创建多语言推送通知{#creating-a-multilingual-push-notification}

## 关于多语言推送通知 {#about-multilingual-push-notification}

根据用户首选的语言和区域发送消息，以个性化推送通知内容。 您可以在内容编辑器中直接导入多语言推送通知内容变体，并在单个投放中发送多语言推送通知。

此功能可利用在收件人的配置文件中指定的首选语言或移动设备应用程序订阅者的系统语言首选项，具体取决于用于推送通知的投放模板。 如果未为特定用户填充语言首选项，则系统将使用创建多语言推送通知时定义的默认变体。 有关如何管理用户档案和订阅者的更多信息，请参阅本[指南](../../audiences/using/get-started-profiles-and-audiences.md)。

![](assets/multivariant_push_1.png)

要将多语言内容变体用于推送通知交付，请执行以下步骤：

* [步骤1:上传多语言内容变体](#step-1--upload-multilingual-content-variant)
* [步骤2:使用多语言内容变体预览和完成推送通知](#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants)
* [步骤3:发送和分析多语言推送通知投放](#step-3--send-and-analyze-multilingual-push-notification-delivery)

## 步骤1:上传多语言内容变体 {#step-1--upload-multilingual-content-variant}

在个性化您的多语言推送通知之前，我们首先需要在多语言投放模板中上传内容变体并创建投放。

>[!NOTE]
>
>如果要为每个语言变体手动创建变体，也可以跳过此步骤。

1. 在&#x200B;**[!UICONTROL Marketing activities]**&#x200B;中，单击&#x200B;**[!UICONTROL Create]**&#x200B;按钮，然后选择&#x200B;**[!UICONTROL Push notification]**。
1. 如果要定向订阅了您移动应用程序的Adobe Campaign用户档案或模板&#x200B;**[!UICONTROL Send multilingual push to app subscriber]**，以向选择从移动应用程序接收通知的所有用户发送推送通知，请选择模板&#x200B;**[!UICONTROL Send multilingual push to Campaign profiles]**。

   ![](assets/multivariant_push_2.png)

1. 在&#x200B;**[!UICONTROL Associate a Mobile App to a delivery]**&#x200B;字段中输入推送通知属性，然后选择移动设备应用程序。

   请注意，此下拉菜单将同时显示SDK V4和Adobe Experience Platform SDK应用程序。

1. 在&#x200B;**[!UICONTROL Audiences]**&#x200B;窗口中，拖放查询以优化受众。

   添加的查询取决于所选的模板：如果选择&#x200B;**[!UICONTROL Send multilingual push to Campaign profiles]**&#x200B;模板，则可以查询移动应用程序的已知收件人。 而如果您选择了&#x200B;**[!UICONTROL Send multilingual push to app subscriber]**&#x200B;模板，则可以查询已选择加入的特定应用程序的所有订阅者。
   >[!NOTE]
   >
   >如果您定位的受众具有特定语言，则需要在CSV文件中列出每种定向语言。

   ![](assets/push_notif_audience.png)

1. 在&#x200B;**[!UICONTROL Manage Content Variants]**&#x200B;窗口中，拖放文件或从计算机中选择文件。

   文件必须采用UTF8编码，并且必须具有特定布局，可通过单击&#x200B;**[!UICONTROL Download the sample file]**&#x200B;选项找到该布局。 您还应使用正确的语法来表示区域设置值。 有关文件格式和支持的区域设置的更多信息，请参阅此[技术说明](https://helpx.adobe.com/cn/campaign/kb/acs-generate-csv-multilingual-push.html)。

   ![](assets/multivariant_push_4.png)

1. 上传文件后，语言变体会自动填充到&#x200B;**[!UICONTROL Variants]**&#x200B;选项卡中。 请注意，如果未为目标用户指定首选语言，则可以在文件中提供&#x200B;**[!UICONTROL Default variant]**，该变量将成为默认内容变体。

   ![](assets/multivariant_push_5.png)

1. **[!UICONTROL Variant selection]**&#x200B;选项卡将提供一个脚本，用于根据投放模板确定要考虑的语言首选项。 这是一个现成的脚本，不需要您进行任何更改。
1. 如果要添加导入文件中不存在的更多变体，可通过单击&#x200B;**[!UICONTROL Add an element]**&#x200B;按钮并根据需要添加任意数量的新语言变体来添加。

   通过添加从文件上传的变体以外的变体，不会将任何内容链接到此语言。 您必须直接在投放仪表板中编辑内容。

   ![](assets/multivariant_push_6.png)

1. 配置完成后，单击&#x200B;**[!UICONTROL Create]**。 您始终可以返回到&#x200B;**[!UICONTROL Content variant]**&#x200B;窗口，并从投放仪表板进行一些更改。

   ![](assets/multivariant_push_8.png)

您现在可以开始个性化多语言推送通知。

## 步骤2:使用多语言内容变体预览和完成推送通知 {#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants}

现在，在上传包含内容变体的文件后，您可以预览推送通知投放中的不同变体。

除了从文件上传的变体之外，还可以创建和编辑更多变体。

1. 在投放仪表板的&#x200B;**[!UICONTROL Content]**&#x200B;窗口中，利用下拉列表，可根据所选语言预览推送通知内容。

   ![](assets/multivariant_push_7.png)

1. 如果未为特定语言指定内容变体，请单击预览下方的铃铛图标，以开始向此语言变体添加内容。

   通过单击&#x200B;**[!UICONTROL Content]**&#x200B;窗口，推送通知将表示下拉列表中所选语言的内容。 在此窗口中所做的更改将只影响一种语言。

1. 您还可以单击内容变体以进一步对其进行自定义，例如使用个性化字段进行自定义。

   有关如何自定义推送通知的更多信息，请参阅此[部分](../../channels/using/customizing-a-push-notification.md)。

   ![](assets/multivariant_push_9.png)

1. 如果要添加或删除语言变体，请单击&#x200B;**[!UICONTROL Content variant]**&#x200B;窗口。

   请注意，通过添加新语言，您必须手动向链接到已添加语言的推送通知添加内容。

   ![](assets/multivariant_push_10.png)

您的多语言推送通知投放现已准备就绪，可供发送。

## 步骤3:发送和分析多语言推送通知投放 {#step-3--send-and-analyze-multilingual-push-notification-delivery}

您的多语言内容变体推送通知现已准备就绪，可发送给您的用户。

1. 要开始准备发送，请单击&#x200B;**[!UICONTROL Prepare]**&#x200B;按钮。
1. 在准备完成且没有警告时，您可以单击&#x200B;**[!UICONTROL Confirm]**&#x200B;按钮以开始发送多语言推送。

   ![](assets/multivariant_push_12.png)

1. 成功发送推送通知后，单击&#x200B;**[!UICONTROL Reports]**&#x200B;图标，然后单击&#x200B;**[!UICONTROL Dynamic reports]**&#x200B;以分析交付成功与否。

   ![](assets/multivariant_push_13.png)

1. 选择 **[!UICONTROL Push notification report]**。
1. 将&#x200B;**[!UICONTROL Variant]**&#x200B;维度拖放到面板中，以开始过滤数据。

   ![](assets/multivariant_push_11.png)

您现在可以测量多语言推送通知投放对收件人的影响。

**相关主题：**

* [推送通知报告](../../reporting/using/push-notification-report.md)
* [在工作流中发送推送通知](../../automating/using/push-notification-delivery.md)
* [使用一个工作流联系多语言受众](https://helpx.adobe.com/cn/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)
