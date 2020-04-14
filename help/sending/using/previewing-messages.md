---
title: 预览消息
description: 了解如何在内容编辑器或电子邮件设计器中预览邮件。
page-status-flag: never-activated
uuid: 8dffca95-59fe-4e9b-93cb-73b33ffde020
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 8428f8ac-8ef5-46cd-9d93-10ec0ecd3ded
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 92bbf57f1a6eff67d2551dc83dd8cb5f6b38bd99

---


# 预览投放 {#previewing-messages}

## 预览电子邮件 {#previewing-emails}

Campaign Standard允许您在发送邮件之前预览邮件，以检查其个性化情况以及收件人将如何看到邮件。

消息预览是使用您 **添加到消息目标** 的测试用户档案来执行的。

对于 **电子邮件** ,Campaign Standard允许您使用目标用户档案而不是测试用户档案来预览邮件。 这允许您获得特定用户档案将收到的消息的精确表示形式。 有关此方面的详细信息，请参阅 [使用目标用户档案测试电子邮件](../../sending/using/testing-messages-using-target.md)。

要使用测试预览用户档案消息，请执行以下步骤：

1. 在“电子邮 [件设计器](../../designing/using/designing-content-in-adobe-campaign.md)”中，单击 **[!UICONTROL Preview]** 按钮。

   ![](assets/sending_preview.png)

   桌面视图和电子邮件的响应式移动视图并排显示。

1. 在每个预览期间执行自动防垃圾邮件检查。 单击该 **[!UICONTROL Anti-spam analysis]** 按钮可进一步了解该警告。

   ![](assets/sending_anti-spam_analysis.png)

1. 选择按 **[!UICONTROL Change profile]** 钮以选择要在上测试个性化元素的测试用户档案。

   ![](assets/sending_test-profile.png)

1. 要退出模 **[!UICONTROL Preview]** 式，请单击屏 **[!UICONTROL Edit]** 幕左上角的按钮。

   ![](assets/sending_preview_edit.png)

**相关主题**

* [管理测试用户档案](../../audiences/using/managing-test-profiles.md)
* [使用目标用户档案测试电子邮件](../../sending/using/testing-messages-using-target.md)
* [发送验证](../../sending/using/sending-proofs.md)

## 预览SMS消息 {#previewing-sms}

对于 **SMS消息** ,Campaign Standard允许您使用测试用户档案预览消息。 这允许您获得特定用户档案将收到的消息的精确表示形式。 有关此内容的详细信息，请参阅 [管理测试用户档案](../../audiences/using/managing-test-profiles.md)。

要使用测试预览用户档案SMS消息，请执行以下步骤：

1. 在您填写SMS消 **[!UICONTROL Properties]** 息并选择受众后，您可以个性化投放。 For more information, refer to [section](../../channels/using/personalizing-sms-messages.md).

   ![](assets/sms_preview.png)

1. 个性化内容后，单击 **[!UICONTROL Create]** 以访问窗 **[!UICONTROL Summary]** 口。

1. 在窗口 **[!UICONTROL Summary]** 中，单击以 **[!UICONTROL Content]** 开始预览您的投放。

   ![](assets/sms_preview_2.png)

1. 在工 **[!UICONTROL Preview]** 具栏中单击。

   ![](assets/sms_preview_3.png)

1. 单击 **[!UICONTROL Change profile]** 以选择测试用户档案，然后 **[!UICONTROL Confirm]**。

   ![](assets/sms_preview_4.png)

现在，您可以根据所选的测试用户档案查看消息的确切表示形式。

**相关主题**

* [关于短信消息](../../channels/using/about-sms-messages.md)
* [创建短信消息](../../channels/using/creating-an-sms-message.md)
* [个性化短信消息](../../channels/using/personalizing-sms-messages.md)

## 预览推送通知 {#previewing-push}

对于 **推送通知**,Campaign Standard允许您使用测试用户档案预览消息。 这允许您获得特定用户档案将收到的消息的精确表示形式。 有关此内容的详细信息，请参阅 [管理测试用户档案](../../audiences/using/managing-test-profiles.md)。

要使用测试预览用户档案推送通知，请执行以下步骤：

1. 在填写推送通 **[!UICONTROL Properties]** 知并选择受众后，您可以个性化投放。 有关详细信息，请参阅自 [定义推送通知](../../channels/using/customizing-a-push-notification.md)。

1. 个性化内容后，您可以根据设备和操作系统在预览窗口中直接检查推送通知的呈现。

   ![](assets/push_preview.png)

1. 要使用测试预览用户档案推送通知，请单击 **[!UICONTROL Preview with test profile]**。

   ![](assets/push_preview_2.png)

1. 然后选择测试用户档案 **[!UICONTROL Confirm]**。

现在，您可以根据所选的测试用户档案查看消息的确切表示形式。

![](assets/push_preview_3.png)

**相关主题**

* [关于推送通知](../../channels/using/about-push-notifications.md)
* [准备和发送推送通知](../../channels/using/preparing-and-sending-a-push-notification.md)
* [自定义推送通知](../../channels/using/customizing-a-push-notification.md)

## 预览应用程序内消息 {#previewing-in-app}

对于 **应用程序内**,Campaign Standard允许您使用测试用户档案预览消息。 这允许您获得特定用户档案将收到的消息的精确表示形式。 有关此内容的详细信息，请参阅 [管理测试用户档案](../../audiences/using/managing-test-profiles.md)。

要使用测试预览用户档案应用程序内消息，请执行以下步骤：

1. 在您填写应用程序 **[!UICONTROL Properties]****[!UICONTROL Triggers]**&#x200B;内消息后，选择受众并设置您的投放，您便可以个性化您的。 有关详细信息，请参 [阅自定义应用程序内消息](../../channels/using/customizing-an-in-app-message.md)。

1. 个性化内容后，您可以根据预览窗口中的设备和操作系统直接检查应用程序内消息的呈现。

   ![](assets/in_app_preview.png)

1. 要使用测试预览用户档案应用程序内消息，请单击 **[!UICONTROL Preview]**。

   ![](assets/in_app_preview_2.png)

1. 然后选择测试用户档案 **[!UICONTROL Confirm]**。

现在，您可以根据所选的测试用户档案查看消息的确切表示形式。

![](assets/in_app_preview_3.png)

**相关主题**

* [关于应用程序内消息传递](../../channels/using/about-in-app-messaging.md)
* [准备和发送应用程序内消息](../../channels/using/preparing-and-sending-an-in-app-message.md)
* [自定义应用程序内消息](../../channels/using/customizing-an-in-app-message.md)