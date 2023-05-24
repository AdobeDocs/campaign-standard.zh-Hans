---
title: 事务型消息传递限制
description: 瞭解Adobe Campaign Standard中有關交易式訊息的主要建議和限制。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: d6aaec6e-c718-46a2-88e8-7402970def1a
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 67%

---

# 異動訊息最佳作法和限制 {#transactional-messaging-limitations}

<img src="assets/do-not-localize/icon_concepts.svg" width="60px">

本節列出開始建立交易式訊息之前，您應注意的最佳實務和限制。

<!--For more on transactional messages, including on how to configure and create them, see [Getting started with transactional messaging](../../channels/using/getting-started-with-transactional-msg.md).-->

## 权限 {#permissions}

僅限具有下列專案的使用者： [管理](../../administration/using/users-management.md#functional-administrators) 角色可以設定交易式事件並存取交易式訊息。

## 事件設定和發佈 {#design-and-publication}

當您設定和發佈交易式事件時，您需要執行的某些步驟無法還原。 您需要了解以下限制：

* 異動訊息傳送的可用管道包括： **[!UICONTROL Email]**， **[!UICONTROL Mobile (SMS)]** 和 **[!UICONTROL Push notification]**.
* 每个事件配置只能使用一个渠道。请参阅[创建事件](../../channels/using/configuring-transactional-event.md#creating-an-event)。
* 创建事件后，便无法更改渠道。因此，您需要设计一种机制，在某个消息未成功发送时，允许通过某种工作流从其他渠道发送该消息。请参阅[工作流数据和流程](../../automating/using/get-started-workflows.md)。
* 创建事件后，就无法再更改定向维度（**[!UICONTROL Real-time event]** 或 **[!UICONTROL Profile]**）。请参阅[创建事件](../../channels/using/configuring-transactional-event.md#creating-an-event)。
* 无法回滚发布，但您可以取消发布事件：此操作会使事件和相关的事务型消息变为无法访问状态。请参阅[取消发布事件](../../channels/using/publishing-transactional-event.md#unpublishing-an-event)。
* 唯一可以与事务型消息关联的事件，就是发布该事件时自动创建的消息。请参阅[预览和发布事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)。

## 異動訊息的數量 {#transactional-message-number}

已發佈的交易式訊息數量可能會對您的平台產生重大影響。 為獲得最佳效能，已發佈的異動訊息數應維持在100以下。 為確保此，請取消發佈或刪除任何未使用的交易式訊息。 另請參閱 [取消發佈交易式訊息](../../channels/using/publishing-transactional-message.md#unpublishing-a-transactional-message) 和 [刪除交易式訊息](../../channels/using/publishing-transactional-message.md#deleting-a-transactional-message).

為確保最佳效能，您也可以取消發佈或刪除未使用的事件。 事實上，取消發佈或刪除事件也會取消發佈或刪除對應的交易式訊息，以及其傳送和追蹤記錄（如有）。 另請參閱 [取消發佈事件](../../channels/using/publishing-transactional-event.md#unpublishing-an-event) 和 [刪除事件](../../channels/using/publishing-transactional-event.md#deleting-an-event).

## 个性化 {#personalization}

个性化消息内容的方式，取决于事务型消息的类型。具體情況列於下方。

### 事件型交易式訊息

* 个性化信息来自事件本身包含的数据。另請參閱 [事件型交易式訊息設定](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages).
* 您 **無法** use **[!UICONTROL Unsubscription link]** 事件交易式訊息中的內容區塊。
* 基于事件的事务型消息，应仅使用已发送事件中的数据来定义收件人和个性化消息内容。但是，您也可以使用 Adobe Campaign 数据库中的信息扩充事务型消息的内容。另請參閱 [豐富化事件](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) 和 [個人化交易式訊息](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message).
* 由于事件事务型消息不包含用户档案信息，所以就算使用用户档案扩充了内容，也不兼容疲劳规则。

### 設定檔交易式訊息

* 个性化信息可以来自事件中包含的数据，也可以来自协调的用户档案记录。另請參閱 [設定檔交易式訊息設定](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages) 和 [設定檔交易式訊息特性](../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities).
* 您 **可以** use **[!UICONTROL Unsubscription link]** 設定檔交易式訊息中的內容區塊。 请参阅[添加内容块](../../designing/using/personalization.md#adding-a-content-block)。
* 疲劳规则与用户档案事务型消息兼容。请参阅[疲劳规则](../../sending/using/fatigue-rules.md)。

### 產品清單

請注意，產品清單可在交易中使用 **電子郵件訊息** 僅限。 请参阅[在事务型消息中使用产品清单](../../designing/using/using-product-listings.md)。

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
