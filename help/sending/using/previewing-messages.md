---
title: 预览消息
description: 了解如何在内容编辑器或Email Designer中预览消息。
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
feature: Seed Address
role: User
level: Intermediate
exl-id: ac8c1265-f530-4438-ab2d-3ca17615ca85
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 15%

---

# 预览投放 {#previewing-messages}

## 预览电子邮件 {#previewing-emails}

Campaign Standard允许您在发送前预览消息，以检查消息的个性化以及收件人将如何看到消息。

使用您添加到消息目标的&#x200B;**测试用户档案**&#x200B;执行消息预览。

对于&#x200B;**email**&#x200B;消息，使用Campaign Standard可以使用目标用户档案而不是测试用户档案预览消息。 这样，您就可以获得特定用户档案将收到的消息的确切呈现形式。 有关更多信息，请参阅[使用定向用户档案测试电子邮件消息](../../sending/using/testing-messages-using-target.md)。

要使用测试用户档案预览消息，请执行以下步骤：

1. 在[Email Designer](../../designing/using/designing-content-in-adobe-campaign.md)中，单击&#x200B;**[!UICONTROL Preview]**&#x200B;按钮。

   ![](assets/sending_preview.png)

   电子邮件的桌面视图和响应式移动视图并排显示。

1. 在每次预览期间执行自动防垃圾邮件检查。 单击&#x200B;**[!UICONTROL Anti-spam analysis]**&#x200B;按钮以了解有关警告的更多信息。

   ![](assets/sending_anti-spam_analysis.png)

1. 选择&#x200B;**[!UICONTROL Change profile]**&#x200B;按钮以选择要测试个性化元素的测试用户档案。

   ![](assets/sending_test-profile.png)

1. 要退出&#x200B;**[!UICONTROL Preview]**&#x200B;模式，请单击屏幕左上角的&#x200B;**[!UICONTROL Edit]**&#x200B;按钮。

   ![](assets/sending_preview_edit.png)

**相关主题**

* [管理测试用户档案](../../audiences/using/managing-test-profiles.md)
* [使用目标用户档案测试电子邮件](../../sending/using/testing-messages-using-target.md)
* [发送校样](../../sending/using/sending-proofs.md)

## 预览短信消息 {#previewing-sms}

对于&#x200B;**SMS**&#x200B;消息，使用Campaign Standard可使用测试用户档案预览消息。 这样，您就可以获得特定用户档案将收到的消息的确切呈现形式。 有关更多信息，请参阅[管理测试用户档案](../../audiences/using/managing-test-profiles.md)。

要使用测试用户档案预览短信消息，请执行以下步骤：

1. 填写短信消息的&#x200B;**[!UICONTROL Properties]**&#x200B;并选择受众后，即可个性化投放。 有关更多信息，请参阅[部分](../../channels/using/personalizing-sms-messages.md)。

   ![](assets/sms_preview.png)

1. 个性化内容后，单击&#x200B;**[!UICONTROL Create]**&#x200B;以访问&#x200B;**[!UICONTROL Summary]**&#x200B;窗口。

1. 在&#x200B;**[!UICONTROL Summary]**&#x200B;窗口中，单击&#x200B;**[!UICONTROL Content]**&#x200B;以开始预览投放。

   ![](assets/sms_preview_2.png)

1. 单击工具栏中的&#x200B;**[!UICONTROL Preview]**。

   ![](assets/sms_preview_3.png)

1. 单击&#x200B;**[!UICONTROL Change profile]**&#x200B;以选择测试用户档案，然后选择&#x200B;**[!UICONTROL Confirm]**。

   ![](assets/sms_preview_4.png)

现在，您可以根据选定的测试用户档案查看消息的确切呈现形式。

**相关主题**

* [关于短信消息](../../channels/using/about-sms-messages.md)
* [创建短信消息](../../channels/using/creating-an-sms-message.md)
* [个性化短信消息](../../channels/using/personalizing-sms-messages.md)

## 预览推送通知 {#previewing-push}

对于&#x200B;**推送通知**，使用Campaign Standard可使用测试用户档案预览消息。 这样，您就可以获得特定用户档案将收到的消息的确切呈现形式。 有关更多信息，请参阅[管理测试用户档案](../../audiences/using/managing-test-profiles.md)。

要使用测试用户档案预览推送通知，请执行以下步骤：

1. 填写推送通知的&#x200B;**[!UICONTROL Properties]**&#x200B;并选择受众后，即可个性化投放。 有关更多信息，请参阅[自定义推送通知](../../channels/using/customizing-a-push-notification.md)。

1. 个性化内容后，您可以根据预览窗口中的设备和操作系统直接检查推送通知的渲染。

   ![](assets/push_preview.png)

1. 要使用测试用户档案预览推送通知，请单击&#x200B;**[!UICONTROL Preview with test profile]**。

   ![](assets/push_preview_2.png)

1. 选择测试用户档案，然后选择&#x200B;**[!UICONTROL Confirm]**。

现在，您可以根据选定的测试用户档案查看消息的确切呈现形式。

![](assets/push_preview_3.png)

**相关主题**

* [关于推送通知](../../channels/using/about-push-notifications.md)
* [准备和发送推送通知](../../channels/using/preparing-and-sending-a-push-notification.md)
* [自定义推送通知](../../channels/using/customizing-a-push-notification.md)

## 预览应用程序内消息 {#previewing-in-app}

对于&#x200B;**应用程序内**，使用Campaign Standard可使用测试用户档案预览消息。 这样，您就可以获得特定用户档案将收到的消息的确切呈现形式。 有关更多信息，请参阅[管理测试用户档案](../../audiences/using/managing-test-profiles.md)。

要使用测试用户档案预览应用程序内消息，请执行以下步骤：

1. 填写应用程序内消息的&#x200B;**[!UICONTROL Properties]**、选择受众并设置&#x200B;**[!UICONTROL Triggers]**&#x200B;后，即可个性化投放。 有关更多信息，请参阅[自定义应用程序内消息](../../channels/using/customizing-an-in-app-message.md)。

1. 个性化内容后，您可以根据预览窗口中的设备和操作系统，直接检查应用程序内消息的渲染。

   ![](assets/in_app_preview.png)

1. 要使用测试用户档案预览应用程序内消息，请单击&#x200B;**[!UICONTROL Preview]**。

   ![](assets/in_app_preview_2.png)

1. 选择测试用户档案，然后选择&#x200B;**[!UICONTROL Confirm]**。

现在，您可以根据选定的测试用户档案查看消息的确切呈现形式。

![](assets/in_app_preview_3.png)

**相关主题**

* [关于应用程序内消息传递](../../channels/using/about-in-app-messaging.md)
* [准备和发送应用程序内消息](../../channels/using/preparing-and-sending-an-in-app-message.md)
* [自定义应用程序内消息](../../channels/using/customizing-an-in-app-message.md)
