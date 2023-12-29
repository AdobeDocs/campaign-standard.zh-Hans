---
title: 事务型消息传递限制
description: 了解Adobe Campaign Standard中有关事务型消息的主要建议和限制。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: d6aaec6e-c718-46a2-88e8-7402970def1a
source-git-commit: 2d3ef53d5ea5603d90da169366be6ea516d96823
workflow-type: tm+mt
source-wordcount: '756'
ht-degree: 61%

---

# 事务型消息传递最佳实践和限制 {#transactional-messaging-limitations}

<img src="assets/do-not-localize/icon_concepts.svg" width="60px">

本节列出了在开始创建事务型消息之前应了解的最佳实践和限制。

<!--For more on transactional messages, including on how to configure and create them, see [Getting started with transactional messaging](../../channels/using/getting-started-with-transactional-msg.md).-->

## 权限 {#permissions}

仅限具有下列属性的用户： [管理](../../administration/using/users-management.md#functional-administrators) 角色可以配置事务性事件并访问事务性消息。

## 事件配置和发布 {#design-and-publication}

配置和发布事务事件时，需要执行的某些步骤无法还原。 您需要了解以下限制：

* 事务性消息传递的可用渠道包括： **[!UICONTROL Email]**， **[!UICONTROL Mobile (SMS)]** 和 **[!UICONTROL Push notification]**.
* 每个事件配置只能使用一个渠道。请参阅[创建事件](../../channels/using/configuring-transactional-event.md#creating-an-event)。
* 创建事件后，便无法更改渠道。因此，您需要设计一种机制，在某个消息未成功发送时，允许通过某种工作流从其他渠道发送该消息。请参阅[工作流数据和流程](../../automating/using/get-started-workflows.md)。
* 创建事件后，就无法再更改定向维度（**[!UICONTROL Real-time event]** 或 **[!UICONTROL Profile]**）。请参阅[创建事件](../../channels/using/configuring-transactional-event.md#creating-an-event)。
* 无法回滚发布，但您可以取消发布事件：此操作会使事件和相关的事务型消息变为无法访问状态。请参阅[取消发布事件](../../channels/using/publishing-transactional-event.md#unpublishing-an-event)。
* 唯一可以与事务型消息关联的事件，就是发布该事件时自动创建的消息。请参阅[预览和发布事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)。

## 事务性消息数 {#transactional-message-number}

已发布的事务性消息的数目可能会对您的平台产生重大影响。 为获得最佳性能，已发布的事务性消息数应保持在100以下，否则可能会发生性能下降。 要确保这一点，请取消发布或删除任何未使用的事务型消息，以满足上述护栏要求。 请参阅 [取消发布事务型消息](../../channels/using/publishing-transactional-message.md#unpublishing-a-transactional-message) 和 [删除事务型消息](../../channels/using/publishing-transactional-message.md#deleting-a-transactional-message).

为确保获得最佳性能，您还可以取消发布或删除未使用的事件。 事实上，取消发布或删除事件也将取消发布或删除相应的事务型消息及其发送和跟踪日志（如果有）。 请参阅 [取消发布事件](../../channels/using/publishing-transactional-event.md#unpublishing-an-event) 和 [删除事件](../../channels/using/publishing-transactional-event.md#deleting-an-event).

## 个性化 {#personalization}

个性化消息内容的方式，取决于事务型消息的类型。具体情况如下所列。

### 基于事件的事务型消息

* 个性化信息来自事件本身包含的数据。请参阅 [基于事件的事务型消息配置](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages).
* 您 **无法** 使用 **[!UICONTROL Unsubscription link]** 事件事务型消息中的内容块。
* 基于事件的事务型消息，应仅使用已发送事件中的数据来定义收件人和个性化消息内容。但是，您也可以使用 Adobe Campaign 数据库中的信息扩充事务型消息的内容。请参阅 [丰富事件](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) 和 [个性化事务型消息](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message).
* 由于事件事务型消息不包含用户档案信息，因此就算使用用户档案扩充了内容，也不兼容疲劳规则。

### 基于用户档案的事务型消息

* 个性化信息可以来自事件中包含的数据，也可以来自协调的用户档案记录。请参阅 [基于用户档案的事务型消息配置](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages) 和 [基于用户档案的事务型消息特性](../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities).
* 您 **可以** 使用 **[!UICONTROL Unsubscription link]** 用户档案事务型消息中的内容块。 请参阅[添加内容块](../../designing/using/personalization.md#adding-a-content-block)。
* 疲劳规则与用户档案事务型消息兼容。请参阅[疲劳规则](../../sending/using/fatigue-rules.md)。

### 产品列表

请注意，产品清单在事务型中可用 **电子邮件消息** 仅限。 请参阅[在事务型消息中使用产品清单](../../designing/using/using-product-listings.md)。

## 品牌化 {#permissions-and-branding}

对于[品牌策略](../../administration/using/branding.md)的管理而言，事务型消息的灵活性低于标准消息。Adobe 建议将事务型消息中使用的所有品牌关联到 **[!UICONTROL All]** [组织单位](../../administration/using/organizational-units.md)。有关此方面的更多信息，请阅读下方的详细说明。

编辑事务型消息时，您可以将其链接到品牌以自动应用一些参数，例如品牌名称或品牌徽标。默认情况下，事务型消息属性中会选中 **[!UICONTROL Default brand]**。

![](assets/message-center_branding.png)

事务型消息中使用的所有对象（包括品牌）都必须在 **[!UICONTROL Message Center]** 组织单位中可见，这意味着这些对象必须在 **[!UICONTROL Message Center]** 或 **[!UICONTROL All]** 组织单位中。

但是，如果消息属性中选择的品牌链接到与 **[!UICONTROL Message Center]** 或 **[!UICONTROL All]** 不同的组织单位，则会导致错误，您将无法发送事务型消息。

因此，如果要在事务型消息的上下文中使用多品牌策略，您应将所有品牌关联到 **[!UICONTROL Message Center]** 组织单位或 **[!UICONTROL All]** 组织单位。

## 导出和导入事务型消息 {#exporting-and-importing-transactional-messages}

* 要导出事务型消息，您需要在[创建导出资源包](../../automating/using/managing-packages.md#creating-a-package)时包含相应的事件配置。
* [通过资源包导入](../../automating/using/managing-packages.md#importing-a-package)事务型消息后，该消息不会显示在事务型消息的列表中。您需要[发布](../../channels/using/publishing-transactional-event.md)事件配置，以使关联的事务型消息可用。
