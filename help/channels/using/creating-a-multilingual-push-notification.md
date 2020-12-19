---
solution: Campaign Standard
product: campaign
title: 创建多语言推送通知
description: 创建多语言推送通知，以目标用户首选语言和地区。
audience: channels
content-type: reference
topic-tags: push-notifications
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 3%

---


# 创建多语言推送通知{#creating-a-multilingual-push-notification}

## 关于多语言推送通知{#about-multilingual-push-notification}

根据用户喜欢的语言和区域发送消息，个性化推送通知内容。 您可以直接在内容编辑器中导入多语言推送通知内容变体，并在单个投放发送多语言推送通知。

此功能根据用于推送通知的收件人，利用投放模板用户档案中指定的首选语言或移动应用程序订阅者的系统语言首选项。 如果未为特定用户填充语言首选项，则系统将使用在创建多语言推送通知时定义的默认变体。 有关如何管理用户档案和订阅者的详细信息，请参阅此[指南](../../audiences/using/get-started-profiles-and-audiences.md)。

![](assets/multivariant_push_1.png)

要将多语言内容变体用于推送通知投放，请执行以下步骤：

* [第1步：上传多语言内容变体](#step-1--upload-multilingual-content-variant)
* [第2步：预览并使用多语言内容变体完成推送通知](#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants)
* [第3步：发送和分析多语言推送通知投放](#step-3--send-and-analyze-multilingual-push-notification-delivery)

## 第1步：上传多语言内容变体{#step-1--upload-multilingual-content-variant}

在个性化您的多语言推送通知之前，我们首先需要在多语言投放模板中上传内容变体并创建投放。

>[!NOTE]
>
>如果要为每个语言变体手动创建变体，则还可以跳过此步骤。

1. 在&#x200B;**[!UICONTROL Marketing activities]**&#x200B;中，单击&#x200B;**[!UICONTROL Create]**&#x200B;按钮，然后选择&#x200B;**[!UICONTROL Push notification]**。
1. 如果要目标已订阅移动应用程序的Adobe Campaign用户档案或模板&#x200B;**[!UICONTROL Send multilingual push to app subscriber]**，请选择模板&#x200B;**[!UICONTROL Send multilingual push to Campaign profiles]**，向已选择接收移动应用程序通知的所有用户发送推送通知。

   ![](assets/multivariant_push_2.png)

1. 输入您的推送通知属性，并在&#x200B;**[!UICONTROL Associate a Mobile App to a delivery]**&#x200B;字段中选择您的移动应用程序。

   请注意，下拉列表将同时显示SDK V4和Adobe Experience PlatformSDK应用程序。

1. 在&#x200B;**[!UICONTROL Audiences]**&#x200B;窗口中，拖放查询以微调受众。

   添加的查询取决于所选的模板：如果选择&#x200B;**[!UICONTROL Send multilingual push to Campaign profiles]**&#x200B;模板，则可以查询移动应用程序的已知收件人。 而如果选择&#x200B;**[!UICONTROL Send multilingual push to app subscriber]**&#x200B;模板，则可以查询已选择某个特定应用程序的所有订阅者。
   >[!NOTE]
   >
   >如果您目标具有特定语言的受众，您需要在CSV文件中列表每种目标语言。

   ![](assets/push_notif_audience.png)

1. 在&#x200B;**[!UICONTROL Manage Content Variants]**&#x200B;窗口中，拖放文件或从计算机中选择一个文件。

   文件必须采用UTF8编码，并且必须具有特定布局，可以通过单击&#x200B;**[!UICONTROL Download the sample file]**&#x200B;选项找到该布局。 您还应对区域设置值使用正确的语法。 有关文件格式和支持的区域设置的详细信息，请参阅此[技术说明](https://helpx.adobe.com/cn/campaign/kb/acs-generate-csv-multilingual-push.html)。

   ![](assets/multivariant_push_4.png)

1. 上传文件后，语言变体会自动填充到&#x200B;**[!UICONTROL Variants]**&#x200B;选项卡中。 请注意，如果未为目标用户指定首选语言，您可以在文件中提供&#x200B;**[!UICONTROL Default variant]**，该变量将是您的默认内容变体。

   ![](assets/multivariant_push_5.png)

1. **[!UICONTROL Variant selection]**&#x200B;选项卡将提供一个脚本，根据投放模板确定要考虑的语言首选项。 这是一个现成的脚本，不需要您进行任何更改。
1. 如果要添加导入文件中不存在的更多变体，可以单击&#x200B;**[!UICONTROL Add an element]**&#x200B;按钮并根据需要添加任意数量的新语言变体。

   通过添加从文件上载的变体以外的变体，不会将任何内容链接到此语言。 您必须直接在投放仪表板中编辑内容。

   ![](assets/multivariant_push_6.png)

1. 完成配置后，单击&#x200B;**[!UICONTROL Create]**。 您始终可以返回&#x200B;**[!UICONTROL Content variant]**&#x200B;窗口，并从投放仪表板进行一些更改。

   ![](assets/multivariant_push_8.png)

您现在可以开始个性化多语言推送通知。

## 第2步：预览并使用多语言内容变体{#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants}完成推送通知

上传包含内容变体的文件后，您现在可以从推送通知预览中投放不同的变体。

除了从文件上传的变体外，还可以创建和编辑更多变体。

1. 在投放仪表板的&#x200B;**[!UICONTROL Content]**&#x200B;窗口中，下拉框允许您根据所选语言预览推送通知内容。

   ![](assets/multivariant_push_7.png)

1. 如果未为特定语言指定内容变体，请单击预览下的铃图标，以开始向此语言变体添加内容。

   通过单击&#x200B;**[!UICONTROL Content]**&#x200B;窗口，推送通知将代表下拉列表中所选语言的内容。 在此窗口中所做的更改只会影响一种语言。

1. 您还可以单击某个内容变体以进一步自定义它，例如使用个性化字段。

   有关如何自定义推送通知的详细信息，请参阅此[部分](../../channels/using/customizing-a-push-notification.md)。

   ![](assets/multivariant_push_9.png)

1. 如果要添加或删除语言变体，请单击&#x200B;**[!UICONTROL Content variant]**&#x200B;窗口。

   请注意，通过添加新语言，您必须手动向链接到所添加语言的推送通知中添加内容。

   ![](assets/multivariant_push_10.png)

您的多语言推送通知投放现已准备就绪。

## 第3步：发送和分析多语言推送通知投放{#step-3--send-and-analyze-multilingual-push-notification-delivery}

您的多语言内容变体推送通知现已准备好发送给您的用户。

1. 要开始准备发送，请单击&#x200B;**[!UICONTROL Prepare]**&#x200B;按钮。
1. 准备完成时，无警告，可单击&#x200B;**[!UICONTROL Confirm]**&#x200B;按钮开始发送多语言推送。

   ![](assets/multivariant_push_12.png)

1. 成功发送推送通知后，单击&#x200B;**[!UICONTROL Reports]**&#x200B;图标，然后单击&#x200B;**[!UICONTROL Dynamic reports]**&#x200B;以分析投放成功与否。

   ![](assets/multivariant_push_13.png)

1. 选择 **[!UICONTROL Push notification report]**。
1. 将&#x200B;**[!UICONTROL Variant]**&#x200B;维拖放到面板中以开始筛选数据。

   ![](assets/multivariant_push_11.png)

您现在可以衡量多语言推送通知投放对收件人的影响。

**相关主题：**

* [推送通知报告](../../reporting/using/push-notification-report.md)
* [在工作流中发送推送通知](../../automating/using/push-notification-delivery.md)
* [使用一个工作流程触及多语言受众](https://helpx.adobe.com/cn/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)
