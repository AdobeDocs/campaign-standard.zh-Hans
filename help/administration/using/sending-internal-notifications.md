---
title: 发送内部通知
description: 了解如何向Adobe Campaign用户发送实时系统通知。
page-status-flag: 从未激活
uuid: f196f025-dbb9-4268-9d7d-ff626994b447
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 管理
content-type: 参考
topic-tags: application-settings
discoiquuid: 4d51229a-745a-4f24-b1c2-22fa203b499c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 发送内部通知{#sending-internal-notifications}

Adobe Campaign允许您直接在应用程序中接收有关重要系统活动的通知。 实时通知可让相关利益相关方及时获得通知，并使用户能够立即直接从应用程序内对活动通知采取行动。 团队的成果是高级敏捷性、效率和更顺畅的营销活动执行。

![](assets/pulse_3.png)

您可以为以下对象配置通知：

* **[!UICONTROL A/B Test emails]**:电子邮件创建者和修改者会被通知已选择变体（自动模式）或需要选择变体（手动模式）。 单击通知会显示相应的电子邮件。 默认情况下，通知会在现成的A/B测试模板中激活。 如果要取消激活它们，请编辑电子邮件或电子邮件模板的属性，并取消选中“常规”&gt;“通 **知”下的框**。 有关A/B测试电子邮件的详细信息，请参阅 [创建AB测试](../../channels/using/designing-an-a-b-test-email.md)。 有关电子邮件属性的详细信息，请参 [阅电子邮件属性列表](../../administration/using/configuring-email-channel.md#list-of-email-properties)。

   ![](assets/pulse_2.png)

* **[!UICONTROL Workflows]**:每当工作流出错时，将通知选定安全组的每个成员（电子邮件和应用程序内通知）。 单击通知或电子邮件链接会显示相应的工作流。 默认情况下，通知在现成工作流模板中处于停用状态。 如果要激活它们，请编辑工作流或工作流模板的属性，并在“常规”&gt;“执行”&gt;“错误管理”&gt;“监 **督者”下添加一个安全组**。 有关安全组的详细信息，请参阅管 [理组和用户](../../administration/using/managing-groups-and-users.md)。 有关工作流属性的详细信息，请参 [阅工作流属性](../../automating/using/executing-a-workflow.md#workflow-properties)。

   ![](assets/pulse_1.png)

