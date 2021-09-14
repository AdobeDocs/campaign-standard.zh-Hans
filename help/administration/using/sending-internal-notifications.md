---
title: 发送内部通知
description: 了解如何向Adobe Campaign用户发送实时系统通知。
audience: administration
content-type: reference
topic-tags: application-settings
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 7e04275a-5413-4f03-b18c-b64ab482d7d5
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 2%

---

# 发送内部通知{#sending-internal-notifications}

Adobe Campaign允许您直接在应用程序中接收有关重要系统活动的通知。 实时通知可让相关利益相关方随时了解情况，并让用户能够从应用程序内立即直接对活动通知采取行动。 团队的成果是提高敏捷性、高效性并更顺畅地执行营销活动。

![](assets/pulse_3.png)

您可以为以下对象配置通知：

* **[!UICONTROL A/B Test emails]**:电子邮件创建者和修改者会收到已选择变体（自动模式）或需要选择变体（手动模式）的通知。单击通知会显示相应的电子邮件。 默认情况下，开箱即用的A/B测试模板中会激活通知。 如果要停用它们，请编辑电子邮件或电子邮件模板的属性，然后取消选中位于&#x200B;**General > Notifications**&#x200B;下的复选框。 有关A/B测试电子邮件的更多信息，请参阅[创建AB测试](../../channels/using/designing-an-a-b-test-email.md)。 有关电子邮件属性的更多信息，请参阅[电子邮件属性列表](../../administration/using/configuring-email-channel.md#list-of-email-properties)。

   ![](assets/pulse_2.png)

* **[!UICONTROL Workflows]**:当工作流出错时，系统会通知选定安全组的每个成员（电子邮件和应用程序内通知）。单击通知或电子邮件链接可显示相应的工作流。 默认情况下，现成工作流模板中会停用通知。 如果要激活它们，请编辑工作流或工作流模板的属性，并在&#x200B;**常规>执行>错误管理>监事**&#x200B;下添加安全组。 有关安全组的更多信息，请参阅[管理组和用户](../../administration/using/managing-groups-and-users.md)。 有关工作流属性的更多信息，请参阅[工作流属性](../../automating/using/managing-execution-options.md)。

   ![](assets/pulse_1.png)
