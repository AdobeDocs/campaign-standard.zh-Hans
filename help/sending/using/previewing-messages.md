---
solution: Campaign Standard
product: campaign
title: 预览消息
description: 了解如何在内容编辑器或电子邮件设计器中预览邮件。
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 15%

---


# 预览投放 {#previewing-messages}

## 预览电子邮件{#previewing-emails}

Campaign Standard允许您在发送邮件前预览邮件，以检查其个性化情况以及收件人将如何看到邮件。

消息预览是使用您添加到消息目标的&#x200B;**测试用户档案**&#x200B;执行的。

对于&#x200B;**email**&#x200B;消息，Campaign Standard允许您使用目标用户档案预览消息，而不是测试用户档案。 这允许您获得特定用户档案将收到的消息的精确表示形式。 有关更多信息，请参阅[使用定向用户档案测试电子邮件消息](../../sending/using/testing-messages-using-target.md)。

要使用测试预览用户档案消息，请执行以下步骤：

1. 在[电子邮件设计器](../../designing/using/designing-content-in-adobe-campaign.md)中，单击&#x200B;**[!UICONTROL Preview]**&#x200B;按钮。

   ![](assets/sending_preview.png)

   电子邮件的桌面视图和响应式移动视图并排显示。

1. 在每个预览期间执行自动防垃圾邮件检查。 单击&#x200B;**[!UICONTROL Anti-spam analysis]**&#x200B;按钮以进一步了解警告。

   ![](assets/sending_anti-spam_analysis.png)

1. 选择&#x200B;**[!UICONTROL Change profile]**&#x200B;按钮以选择要测试个性化元素的测试用户档案。

   ![](assets/sending_test-profile.png)

1. 要退出&#x200B;**[!UICONTROL Preview]**&#x200B;模式，请单击屏幕左上角的&#x200B;**[!UICONTROL Edit]**&#x200B;按钮。

   ![](assets/sending_preview_edit.png)

**相关主题**

* [管理测试用户档案](../../audiences/using/managing-test-profiles.md)
* [使用目标用户档案测试电子邮件](../../sending/using/testing-messages-using-target.md)
* [发送校样](../../sending/using/sending-proofs.md)

## 预览SMS消息{#previewing-sms}

对于&#x200B;**SMS**&#x200B;消息，Campaign Standard允许您使用测试用户档案预览消息。 这允许您获得特定用户档案将收到的消息的精确表示形式。 有关更多信息，请参阅[管理测试用户档案](../../audiences/using/managing-test-profiles.md)。

要使用测试预览用户档案SMS消息，请执行以下步骤：

1. 填写&#x200B;**[!UICONTROL Properties]** SMS消息并选择受众后，您便可以个性化投放。 有关详细信息，请参阅[部分](../../channels/using/personalizing-sms-messages.md)。

   ![](assets/sms_preview.png)

1. 个性化内容后，单击&#x200B;**[!UICONTROL Create]**&#x200B;以访问&#x200B;**[!UICONTROL Summary]**&#x200B;窗口。

1. 在&#x200B;**[!UICONTROL Summary]**&#x200B;窗口中，单击&#x200B;**[!UICONTROL Content]**&#x200B;以开始预览投放。

   ![](assets/sms_preview_2.png)

1. 单击工具栏中的&#x200B;**[!UICONTROL Preview]**。

   ![](assets/sms_preview_3.png)

1. 单击&#x200B;**[!UICONTROL Change profile]**&#x200B;选择测试用户档案，然后选择&#x200B;**[!UICONTROL Confirm]**。

   ![](assets/sms_preview_4.png)

现在，您可以根据选定的测试用户档案，看到消息的确切表示形式。

**相关主题**

* [关于短信消息](../../channels/using/about-sms-messages.md)
* [创建短信消息](../../channels/using/creating-an-sms-message.md)
* [个性化短信消息](../../channels/using/personalizing-sms-messages.md)

## 预览推送通知{#previewing-push}

对于&#x200B;**推送通知**,Campaign Standard允许您使用测试用户档案预览消息。 这允许您获得特定用户档案将收到的消息的精确表示形式。 有关更多信息，请参阅[管理测试用户档案](../../audiences/using/managing-test-profiles.md)。

要使用测试预览用户档案推送通知，请执行以下步骤：

1. 填写推送通知的&#x200B;**[!UICONTROL Properties]**&#x200B;并选择受众后，即可个性化投放。 有关详细信息，请参阅[自定义推送通知](../../channels/using/customizing-a-push-notification.md)。

1. 个性化内容后，您可以根据设备和操作系统在预览窗口中直接检查推送通知的呈现情况。

   ![](assets/push_preview.png)

1. 要使用测试预览用户档案推送通知，请单击&#x200B;**[!UICONTROL Preview with test profile]**。

   ![](assets/push_preview_2.png)

1. 选择测试用户档案，然后选择&#x200B;**[!UICONTROL Confirm]**。

现在，您可以根据选定的测试用户档案，看到消息的确切表示形式。

![](assets/push_preview_3.png)

**相关主题**

* [关于推送通知](../../channels/using/about-push-notifications.md)
* [准备和发送推送通知](../../channels/using/preparing-and-sending-a-push-notification.md)
* [自定义推送通知](../../channels/using/customizing-a-push-notification.md)

## 预览应用程序内消息{#previewing-in-app}

对于&#x200B;**应用程序内**,Campaign Standard允许您使用测试用户档案预览消息。 这允许您获得特定用户档案将收到的消息的精确表示形式。 有关更多信息，请参阅[管理测试用户档案](../../audiences/using/managing-test-profiles.md)。

要使用测试预览用户档案应用程序内消息，请执行以下步骤：

1. 填写应用程序内消息的&#x200B;**[!UICONTROL Properties]**&#x200B;后，选择受众并设置&#x200B;**[!UICONTROL Triggers]**，即可个性化投放。 有关详细信息，请参阅[自定义应用程序内消息](../../channels/using/customizing-an-in-app-message.md)。

1. 个性化内容后，您可以根据设备和操作系统在预览窗口中直接检查应用程序内消息的呈现。

   ![](assets/in_app_preview.png)

1. 要使用测试预览用户档案应用程序内消息，请单击&#x200B;**[!UICONTROL Preview]**。

   ![](assets/in_app_preview_2.png)

1. 选择测试用户档案，然后选择&#x200B;**[!UICONTROL Confirm]**。

现在，您可以根据选定的测试用户档案，看到消息的确切表示形式。

![](assets/in_app_preview_3.png)

**相关主题**

* [关于应用程序内消息传递](../../channels/using/about-in-app-messaging.md)
* [准备和发送应用程序内消息](../../channels/using/preparing-and-sending-an-in-app-message.md)
* [自定义应用程序内消息](../../channels/using/customizing-an-in-app-message.md)