---
title: 确认订阅服务
description: 请按照以下步骤为订阅Adobe Campaign中服务的配置文件设置确认消息。
page-status-flag: 从未激活
uuid: 23e6c4c2-e2c7-472f-b616-36a95225ac1d
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: 参考
topic-tags: 管理订阅
discoiquuid: 1a24504e-7f9d-4297-b39e-c5f085b0f388
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 确认订阅服务{#confirming-subscription-to-a-service}

## 关于发送订阅确认 {#sending-subscription-confirmation}

本节介绍如何向订阅特定服务的配置文件发送自动自定义确认电子邮件。

当您要向服务发送订阅（或取消订阅）的确认消息时，可以使用默认消息或自定义消息。 创建服务部分中显示了选择确认消 [息的步骤](../../audiences/using/creating-a-service.md) 。

如果选择使用默认消息，则可编辑其内容，但有以下限制：
* 您只能使用活动上下文中有限的字段个性化消息内容。
* 对于使用默认模式的所有服务，此消息将是相同的。

要为给定服务发送特定的确认电子邮件，您可以创建自定义消息，在该消息中，您还可以利用来自其他资源的个性化字段。 为此，您必须创建和配置事务性消息。 可以引用此消息：
* 服务本身。 有关详细信息，请参 [阅从服务配置确认消息](#configuring-confirmation-message-from-service)。
* 从订阅登录页面。 有关详细信息，请参 [阅从登陆页面配置确认消息](#configuring-confirmation-message-from-landing-page)。

## 从服务配置确认消息 {#configuring-confirmation-message-from-service}

例如，您希望在网站的访客订阅您的品牌新闻快讯时自动向其发送确认消息。

您需要配置交易电子邮件并从所需服务引用该消息（在此例中订阅品牌新闻快讯）。 为了用服务信息丰富事务消息，您可以在创建事件时定义协调。

从服务配置时，确认事务消息将仅在每个访客首次订阅该服务时发送。 如果配置文件已订阅，则不会再向该配置文件发送确认消息。

### 第1步：创建确认电子邮件 {#step-1--create-the-confirmation-email-1}

系统会自动向订阅新闻稿的每个配置文件发送确认电子邮件（通过登录页面或任何其他方式）。 订阅被视为事件，而电子邮件是一条交易 [消息](../../channels/using/about-transactional-messaging.md) ，它将针对订阅服务的每个配置文件。

创建确认电子邮件的步骤如下所述。 由于事务消息将在服务中引用，因此您需要先创建它。

#### 创建活动 {#create-the-event-1}

确认电子邮件是一条事务性消息，当它对事件作出反应时：服务订阅。 此消息将发送以确认订阅您的新闻稿。

1. 通过 **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt;菜单创 **[!UICONTROL Event configuration]** 建活动，可从Adobe Campaign徽标访问。
1. 输入标签，选择定位维度，然后单击 **[!UICONTROL Create]**。

   配置事务消息部分中介绍 [了配置步骤](../../administration/using/configuring-transactional-messaging.md) 。

1. 在部 **[!UICONTROL Fields]** 分中，单 **[!UICONTROL Create element]** 击并添 **[!UICONTROL publicLabel]** 加到数据结构以启用协调。

   ![](assets/confirmation_publicLabel-field.png)

   >[!NOTE]
   >
   >该字 **[!UICONTROL publicLabel]** 段是必填字段。 如果不将其添加到活动数据结构，则Adobe Campaign将无法与服务进行协调。 订阅服务时，此字段将填入相应服 **[!UICONTROL Service label]** 务的字段。

1. 在部分 **[!UICONTROL Enrichment]** 中，单击并 **[!UICONTROL Create element]** 选择目标 **[!UICONTROL Service]** 资源。

   ![](assets/confirmation_enrichment-service.png)

1. 在部 **[!UICONTROL Join definition]** 分中，将资源的字 **[!UICONTROL publicLabel]** 段与事 **[!UICONTROL Service]** 件配置的字 **[!UICONTROL publicLabel]** 段进行映射。

   ![](assets/confirmation_publicLabel-join.png)

   >[!NOTE]
   >
   >这样，您就可以在交易消息中使用资 **[!UICONTROL Service]** 源中的个性化字段。

1. 保存活动配置，然后单 **[!UICONTROL Publish]** 击以发布活动。

活动已准备就绪。 您现在可以设计交易电子邮件。

#### 设计确认消息 {#design-the-confirmation-message-1}

确认电子邮件是基于您刚刚发布的活动的事务性消息。

1. 从Adobe Campaign徽标中，选择 **[!UICONTROL Marketing plans]** &gt;并 **[!UICONTROL Transactional messages]** 单击 **[!UICONTROL Transactional messages]**。
1. 选择与您刚刚发布的活动对应的交易电子邮件。

1. 单击该 **[!UICONTROL Content]** 部分，然后选择电子邮件模板。 有关编辑事务性消息内容的详细信息，请参阅 [活动事务性消息](../../channels/using/event-transactional-messages.md)。
1. 由于您可以直接访问资源中的所有字段， **[!UICONTROL Service]** 因此可以从&gt; **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event (rtEvent)]** &gt; **[!UICONTROL Event context (ctx)]****[!UICONTROL Service]** &gt;节点中选择任何字段，以个性化您的内容。

   ![](assets/confirmation_personalization-service.png)

   有关个性化交易消息的更多信息，请参 [阅此部分](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message)。

1. 使用测试配置文件预览您的消息。 有关详细信息，请参 [阅在交易消息中定义测试配置文件](../../channels/using/event-transactional-messages.md#defining-a-test-profile-in-a-transactional-message)。

1. 单击 **[!UICONTROL Save & close]** 以保存您的内容。
1. 发布交易消息。 请参 [阅发布交易消息](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)。

### 第2步：创建和配置服务 {#step-2--create-and-configure-the-service-1}

1. 从高级菜单 **Profiles &amp; audiences** &gt; **** Services（通过Adobe Campaign徽标）中，创建服务。
1. 转到该部 **[!UICONTROL Service properties]** 分，可通过服务功能板 ![](assets/edit_darkgrey-24px.png) 中的按钮访问该部分。
1. 填写字 **[!UICONTROL Service label]** 段。

   ![](assets/confirmation_service-label.png)

   >[!NOTE]
   >
   >必须填写此字段才能启用事务消息的对帐。

1. 在部分 **[!UICONTROL Confirmation messages]** 中，选择 **[!UICONTROL Custom message]**:此模式允许您为订阅服务的配置文件引用特定的确认消息。
1. 选择与 **[!UICONTROL Custom subscription event configuration]** 您创建的事务性消息关联的消息。

   ![](assets/confirmation_service-confirmation-message.png)

1. 单击 **[!UICONTROL Confirm]** 并保存服务。

现在，每次配置文件订阅此服务时，他都会收到您定义的交易消息，其中具有映射到选定服务的个性化字段。

>[!NOTE]
>
>仅在用户首次订阅时发送消息。

## 从登陆页面配置确认消息 {#configuring-confirmation-message-from-landing-page}

您还可以使用登录页面部分中的选项从订阅登 **[!UICONTROL Start sending messages]** 陆页面引 **[!UICONTROL Job]** 用确认消息。

从登录页面引用确认消息时，每次提交登录页面时（即使已订阅配置文件）都会发送消息。

### 第1步：创建确认电子邮件 {#step-1--create-the-confirmation-email-2}

将向通过登陆页面订阅新闻稿的每个配置文件自动发送确认电子邮件。 订阅被视为事件，而电子邮件是一条交易消息 [](../../channels/using/about-transactional-messaging.md) ，它将针对订阅服务的每个配置文件。

创建这些元素的步骤如下所述。 由于交易消息将在登陆页面中引用，因此您需要先创建它。

#### 创建活动 {#create-the-event-2}

确认电子邮件是一 [条事务消息](../../channels/using/about-transactional-messaging.md) ，当它对事件作出反应时：服务订阅。 此消息将发送以确认订阅您的新闻稿。

1. 通过 **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt;菜单创 **[!UICONTROL Event configuration]** 建活动，可从Adobe Campaign徽标访问。
1. 输入标签，选择定位维度，然后单击 **[!UICONTROL Create]**。

   配置事务消息部分中介绍 [了配置步骤](../../administration/using/configuring-transactional-messaging.md) 。

1. 在部 **[!UICONTROL Fields]** 分中，单 **[!UICONTROL Create element]** 击并添 **[!UICONTROL serviceName]** 加到数据结构以启用协调。

   ![](assets/confirmation_serviceName-field.png)

   >[!NOTE]
   >
   >该字 **[!UICONTROL serviceName]** 段是必填字段。 如果不将其添加到活动数据结构，则Adobe Campaign将无法与订阅的服务进行协调。

1. 在部分 **[!UICONTROL Enrichment]** 中，单击并 **[!UICONTROL Create element]** 选择目标 **[!UICONTROL Service]** 资源。
1. 在部 **[!UICONTROL Join definition]** 分中，将资源的字 **[!UICONTROL serviceName]** 段与事 **[!UICONTROL Service]** 件配置的字 **[!UICONTROL name]** 段进行映射。

   ![](assets/confirmation_serviceName-join.png)

   >[!NOTE]
   >
   >这样，您就可以在交易消息中使用资 [!UICONTROL Service] 源中的个性化字段。

#### 设计确认消息 {#design-the-confirmation-message-2}

本节介绍了设计事务消息的步 [骤](#design-the-confirmation-message-1)。

### 第2步：创建和配置服务 {#step-2--create-and-configure-the-service-2}

1. 从高级菜单 **[!UICONTROL Profiles & audiences]** &gt;中 **[!UICONTROL Services]** 通过Adobe Campaign徽标创建服务。
1. 转到该部 **[!UICONTROL Service properties]** 分，可通过服务功能板 ![](assets/edit_darkgrey-24px.png) 中的按钮访问该部分。
1. 填写字 **[!UICONTROL Service label]** 段。 此标签将显示在确认消息和订阅登录页面中。
1. 单击 **[!UICONTROL Confirm]** 并保存服务。

### 第3步：创建和配置登陆页面 {#step-3--create-and-configure-the-landing-page}

创建将在您的网站上发布的订阅登录页面。

要创建和配置此登录页面，请执行以下步骤：

1. 根据模 [板设计新的登录](../../channels/using/about-landing-pages.md) 页 **[!UICONTROL Subscription]** 面。
1. 编辑登陆页面属性。 在 **[!UICONTROL Job]** &gt;部 **[!UICONTROL Specific actions]** 分，选择 **[!UICONTROL Specific service]** 选项，然后从下拉列表中选择刚刚创建的服务。

   ![](assets/confirmation_lp-specific-service.png)

1. 选择 **[!UICONTROL Start sending message]** 选项，然后从下拉列表中选择您刚刚创建的事务性消息。

   ![](assets/confirmation_lp-start-sending-message.png)

1. 自定义登录页面的内容。

1. [测试并发布登陆页](../../channels/using/sharing-a-landing-page.md) 。

现在，每当配置文件通过提交登陆页面订阅您的新闻稿时，他都会收到您通过映射到服务的个性化字段定义的确认消息。

>[!NOTE]
>
>每次提交登录页面时，即使配置文件已订阅，也会发送消息。
