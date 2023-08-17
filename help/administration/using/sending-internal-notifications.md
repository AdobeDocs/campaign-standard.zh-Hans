---
title: 发送内部通知
description: 了解如何向Adobe Campaign用户发送实时系统通知
audience: administration
role: Admin
level: Experienced
exl-id: 7e04275a-5413-4f03-b18c-b64ab482d7d5
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 2%

---

# 发送内部通知{#sending-internal-notifications}

通过Adobe Campaign，您可以直接在应用程序中接收有关重要系统活动的通知。 实时通知可随时告知相关利益相关者，并让用户能够立即直接从应用程序内对活动通知采取行动。 对于团队而言，其结果是提高了营销活动的灵活性、效率和平顺执行。

![](assets/pulse_3.png)

您可以为以下对象配置通知：

* **[!UICONTROL A/B Test emails]**：通知电子邮件创建者和修改者，已选择变体（自动模式）或需要选择变体（手动模式）。 单击通知将显示相应的电子邮件。 默认情况下，会在现成的A/B测试模板中激活通知。 如果要取消激活它们，请编辑电子邮件或电子邮件模板的属性，并取消选中位于下的复选框 **“常规”>“通知”**. 有关A/B测试电子邮件的详细信息，请参阅 [创建AB测试](../../channels/using/designing-an-a-b-test-email.md). 有关电子邮件属性的更多信息，请参阅 [电子邮件属性列表](../../administration/using/configuring-email-channel.md#list-of-email-properties).

  ![](assets/pulse_2.png)

* **[!UICONTROL Workflows]**：当工作流出错时，将通知选定安全组的每个成员（电子邮件和应用程序内通知）。 单击通知或电子邮件链接会显示相应的工作流。 默认情况下，现成工作流模板中的通知处于停用状态。 如果要激活它们，请编辑工作流或工作流模板的属性，并在下添加安全组 **常规>执行>错误管理>主管**. 有关安全组的详细信息，请参阅 [管理组和用户](../../administration/using/managing-groups-and-users.md). 有关工作流属性的更多信息，请参阅 [工作流属性](../../automating/using/managing-execution-options.md).

  ![](assets/pulse_1.png)
