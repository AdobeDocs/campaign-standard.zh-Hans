---
solution: Campaign Standard
product: campaign
title: 事务型消息传递限制
description: 了解Adobe Campaign Standard事务性消息的主要限制和建议。
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 87%

---


# 事务型消息传递限制{#transactional-messaging-limitations}

<img src="assets/do-not-localize/icon_concepts.svg" width="60px">

以下部分列表了在开始创建事务性消息之前您应了解的限制。

有关事务性消息的更多信息（包括如何配置和创建这些信息），请参 [阅事务消息快速入门](../../channels/using/getting-started-with-transactional-msg.md)。

>[!IMPORTANT]
>
>要访问事务型消息，您必须具有管理权限。

## 设计和发布{#design-and-publication}

设计和发布事务型消息时，需要执行的某些步骤无法恢复。您需要了解以下限制：

* 每个事件配置只能使用一个渠道。请参阅[创建事件](../../administration/using/configuring-transactional-messaging.md#creating-an-event)。
* 创建事件后，便无法更改渠道。因此，您需要设计一种机制，在某个消息未成功发送时，允许通过某种工作流从其他渠道发送该消息。请参阅[工作流数据和流程](../../automating/using/get-started-workflows.md)。
* 创建事件后，就无法再更改定向维度（**[!UICONTROL Real-time event]** 或 **[!UICONTROL Profile]**）。请参阅[创建事件](../../administration/using/configuring-transactional-messaging.md#creating-an-event)。
* 无法回滚发布，但您可以取消发布事件：此操作会使事件和相关的事务型消息变为无法访问状态。请参阅[取消发布事件](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event)。
* 唯一可以与事务型消息关联的事件，就是发布该事件时自动创建的消息。请参阅[预览和发布事件](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)。

## 个性化{#personalization}

个性化消息内容的方式，取决于事务型消息的类型。具体情况如下。

### 事件事务性消息

* 个性化信息来自事件本身包含的数据。请参阅[事件事务型消息](../../channels/using/event-transactional-messages.md)。
* You **cannot** use **[!UICONTROL Unsubscription link]** content blocks in an event transactional message.
* 基于事件的事务型消息，应仅使用已发送事件中的数据来定义收件人和个性化消息内容。但是，您也可以使用 Adobe Campaign 数据库中的信息扩充事务型消息的内容。请参阅[扩充事务型消息的内容](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)。
* 由于事件事务型消息不包含用户档案信息，所以就算使用用户档案扩充了内容，也不兼容疲劳规则。请参阅[疲劳规则](../../sending/using/fatigue-rules.md)。

### 用户档案事务性消息

* 个性化信息可以来自事件中包含的数据，也可以来自协调的用户档案记录。请参阅[用户档案事务型消息](../../channels/using/profile-transactional-messages.md)。
* You **can** use **[!UICONTROL Unsubscription link]** content blocks in a profile transactional message. 请参阅[添加内容块](../../designing/using/personalization.md#adding-a-content-block)。
* 疲劳规则与用户档案事务型消息兼容。请参阅[疲劳规则](../../sending/using/fatigue-rules.md)。

请注意，产品清单仅可用在事务型电子邮件消息中。请参阅[在事务型消息中使用产品清单](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message)。

## 权限和品牌策略 {#permissions-and-branding}

对于[品牌策略](../../administration/using/branding.md)的管理而言，事务型消息的灵活性低于标准消息。Adobe 建议将事务型消息中使用的所有品牌关联到 **[!UICONTROL All]** [组织单位](../../administration/using/organizational-units.md)。有关此方面的更多信息，请阅读下方的详细说明。

编辑事务型消息时，您可以将其链接到品牌以自动应用一些参数，例如品牌名称或品牌徽标。默认情况下，事务型消息属性中会选中 **[!UICONTROL Default brand]**。

![](assets/message-center_branding.png)

事务型消息中使用的所有对象（包括品牌）都必须在 **[!UICONTROL Message Center]** 组织单位中可见，这意味着这些对象必须在 **[!UICONTROL Message Center]** 或 **[!UICONTROL All]** 组织单位中。

但是，如果消息属性中选择的品牌链接到与 **[!UICONTROL Message Center]** 或 **[!UICONTROL All]** 不同的组织单位，则会导致错误，您将无法发送事务型消息。

因此，如果要在事务型消息的上下文中使用多品牌策略，您应将所有品牌关联到 **[!UICONTROL Message Center]** 组织单位或 **[!UICONTROL All]** 组织单位。

## 导出和导入事务型消息 {#exporting-and-importing-transactional-messages}

* 要导出事务型消息，您需要在[创建导出资源包](../../automating/using/managing-packages.md#creating-a-package)时包含相应的事件配置。
* [通过资源包导入](../../automating/using/managing-packages.md#importing-a-package)事务型消息后，该消息不会显示在事务型消息的列表中。您需要[发布](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)事件配置，以使关联的事务型消息可用。
