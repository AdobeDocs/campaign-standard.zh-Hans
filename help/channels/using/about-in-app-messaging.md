---
title: 关于应用程序内消息传递
description: 在具有应用程序内消息传递功能的移动应用程序中，显示消息或警报。
audience: channels
content-type: reference
topic-tags: in-app-messaging
context-tags: delivery,triggers,back
feature: In App
role: User
exl-id: 986646b1-42d5-4169-ac38-d8e612a9a6d3
source-git-commit: 462ebaf8e8f1f056aa92118226ef77aea37b972b
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 100%

---

# 关于应用程序内消息传递{#about-in-app-messaging}

利用应用程序内消息传递渠道，可向移动应用程序中的活动用户发送消息。这种消息类型可免费将通知推送到用户手机的通知中心。有关推送通知渠道的更多信息，请参阅此[章节](../../channels/using/about-push-notifications.md)。

此渠道要求将移动应用程序与 Adobe Experience Platform SDK 集成。这些应用程序必须先在 Adobe Experience Platform Launch 中激活，然后才能在 Adobe Campaign 中用于应用程序内投放。

![](assets/launch_campaign.png)

要在应用 Experience Platform SDK 的移动应用程序上发送应用程序内消息，您首先需要满足以下先决条件：

1. 在 Adobe Campaign 中，确保可以访问 **[!UICONTROL In-App]** 渠道。如果您无法访问这些渠道，请与帐户管理团队联系。

1. 要在 Adobe Campaign Standard 中使用与 Experience Cloud SDK 应用程序集成的移动使用案例，必须在 Adobe Experience Platform Launch 中创建移动应用，并在 Adobe Campaign Standard 中对其进行配置。有关分步指南，请参阅此[页面](../../administration/using/configuring-a-mobile-application.md)。

1. 配置完毕后，您即可准备应用程序内消息。有关更多信息，请参见此[页面](../../channels/using/preparing-and-sending-an-in-app-message.md#preparing-your-in-app-message)。

1. 然后，您可以决定是发送[应用程序内消息](../../channels/using/customizing-an-in-app-message.md)还是[自定义本地通知消息类型](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type)。

1. 您的投放现已准备就绪，可供发送。要了解更多信息，请参阅此[页面](../../channels/using/preparing-and-sending-an-in-app-message.md#sending-your-in-app-message)。

**相关内容：**

* [应用程序内报告](../../reporting/using/in-app-report.md)
* [Adobe Campaign Standard 中支持的移动使用案例](../../administration/using/configuring-rules-launch.md)
* [Campaign Standard Mobile 指南](../../channels/using/get-started-communication-channels.md)

## 处理具有个人和敏感数据的移动用户档案字段 {#handling-mobile-profile-fields-with-personal-and-sensitive-data}

在 Adobe Campaign 中，由移动设备发出的移动配置文件属性数据存储在 **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** 资源中，利用该资源，您可定义要从应用程序的订阅者那里收集的数据。

需要扩展此资源，才能收集您打算从移动设备发送到 Adobe Campaign 的数据。要实现此目的，请参阅此[页面](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)以了解详细步骤。

为了更安全地实现应用程序内消息的个性化，需要相应地配置此资源中的移动配置文件字段。在 **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** 中创建新移动用户档案字段时，请勾选 **[!UICONTROL Personal and Sensitive]** 以使它们在应用程序内消息个性化期间不可用。

>[!NOTE]
>
>如果此表格中已存在带有自定义资源扩展的现有实施项，我们建议您在将字段用于个性化应用程序内消息之前，为这些字段添加适当的标签。

![](assets/in_app_personal_data_2.png)

配置和发布 **[!UICONTROL Subscriptions to an application]** 自定义资源后，您即可使用 **[!UICONTROL Target users based on their Mobile profile (inApp)]** 模板开始准备应用程序内投放。只有 **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** 资源中的非个人和非敏感字段，才可进行个性化。

如果需要使用 **Personal and Sensitive** 字段进行个性化，我们建议使用 **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]** 模板，此模板可提供额外的安全机制来确保用户 PII 数据的安全。
