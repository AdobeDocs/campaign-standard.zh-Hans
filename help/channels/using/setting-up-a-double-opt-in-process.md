---
title: 设置双重选择启用流程
description: 请按照以下步骤使用多次中的登陆页设置Adobe Campaign选择加入流程。
page-status-flag: never-activated
uuid: 23e6c4c2-e2c7-472f-b616-36a95225ac1d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: 1a24504e-7f9d-4297-b39e-c5f085b0f388
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 012546e109b085b7ed968bcefa8f76482656ae0d
workflow-type: tm+mt
source-wordcount: '1157'
ht-degree: 1%

---


# 设置双重选择启用流程{#setting-up-a-double-opt-in-process}

## 关于多次选择加入 {#about-double-opt-in}

多次选择加入机制是发送电子邮件的最佳实践。 它可保护平台免遭错误或无效的电子邮件地址、垃圾邮件程序，并防止可能的垃圾邮件投诉。

其原则是，在将访客作为“用户档案”存储到活动数据库中之前，先发送一封电子邮件，确认其协议： 访客填写在线登陆页，然后收到电子邮件，并必须单击确认链接才能最终确定订阅。

![](assets/optin_mechanism.png)

要设置此设置，您需要：

1. 创建并发布登陆页，以便访客可以注册和订阅。 此登陆页可从网站获取。 填写并提交此登陆页的访客将存储在库中，但会添加到块列表中，以便在最终验证之前不接收任何通信(请参阅 [活动中的块列表管理](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md))。
1. 自动创建并发送带确认链接的加入电子邮件。 此电子邮件将目标提交登陆页的人群。 它将基于允许目标“选择退出”用户档案的电子邮件模板。
1. 重定向至确认登陆页。 此最终登陆页将提出确认按钮： 访客必须点击它。 您可以设计一封欢迎电子邮件，在确认完成后发送，例如，在电子邮件中为新收件人添加一个特殊优惠。

这些步骤必须按特定顺序以Adobe Campaign设置，才能正确启用所有参数。

## 第1步： 创建确认登陆页 {#step-1--create-the-confirmation-landing-page}

在创建确认多次时，设置登陆页加入机制开始的过程： 当访客单击确认电子邮件以进行注册时，将显示此页。

要创建并配置此登陆页，您需要：

1. 根据模 [板设计](../../channels/using/getting-started-with-landing-pages.md) 一个新的 **[!UICONTROL Profile acquisition (acquisition)]** 登陆页。 输入标签“**CONFIRMATION**”。

   如果您需要使 [用服](../../audiences/using/about-subscriptions.md)务，还可以使用 **[!UICONTROL Subscription (sub)]** 模板。

1. 编辑登陆页属性，在 **[!UICONTROL Access and loading]** 部分中，取消选 **[!UICONTROL Authorize unidentified visitors]**&#x200B;择选 **[!UICONTROL Preload visitor data]** 项，选择（此选项不是强制选项）。

   ![](assets/optin_confirmlp_param.png)

1. 在>部 **[!UICONTROL Job]** 分， **[!UICONTROL Additional data]** 单击并 **[!UICONTROL Add an element]** 输入以下上下文路径：

   /context/用户档案/blockList

   将值设置为 **false** ，然后单击 **[!UICONTROL Add]**。

   ![](assets/optin_confirmlp_newelement.png)

   为了能够发送电子邮件，此上下文将删除“在块列表中”字段。 我们稍后会看到第一个登陆页在确认前将 **此字段** 设置为true，以防止向未确认的用户档案发送电子邮件。 有关此方面的详细信息，请 [参阅步骤3: 创建客户获取登陆页](#step-3--create-the-acquisition-landing-page)。

1. 自定义登陆页的内容： 您可以显示个性化数据，并将确认按钮的标签更改为“单击此处确认我的订阅”。

   ![](assets/optin_confirmlp_design.png)

1. 调整确认页面的内容，以通知订阅者他们已注册。

   ![](assets/optin_confimlp_page2.png)

1. [测试和发布](../../channels/using/testing-publishing-landing-page.md) 登陆页。

## 第2步： 创建确认电子邮件 {#step-2--create-the-confirmation-email}

创建确认登陆页后，您可以设计确认电子邮件： 此电子邮件将自动发送给验证客户赢取登陆页的每位访客。 此验证被视为事件，而电子邮件是事务性消息，链接到允许目标退出人群的特定类型规则。

创建这些元素的步骤如下所述。 您需要在创建客户获取登陆页之前遵循这些模板，因为此电子邮件模板将在其中引用。

### 创建事件 {#create-the-event}

确认电子邮件是一 [个事务性消息](../../channels/using/about-transactional-messaging.md) ，当它对事件做出反应时： 表单的验证。 您必须先创建事件，然后创建事务性消息模板。

1. 从> >菜单创 **[!UICONTROL Marketing plans]** 建事件 **[!UICONTROL Transactional messages]** , **[!UICONTROL Event configuration]** 可从Adobe Campaign徽标访问，然后输入标签“**CONFIRM**”。
1. 选择定位维度 **[!UICONTROL Profile]** 并单击 **[!UICONTROL Create]**。

   ![](assets/optin_eventcreate.png)

1. 在部 **[!UICONTROL Fields]** 分中，单 **[!UICONTROL Create element]** 击并在数 **[!UICONTROL email]** 据结构中添加以启用对帐。
1. 在部分 **[!UICONTROL Enrichment]** 中，单 **[!UICONTROL Create element]** 击并选择 **[!UICONTROL Profile]** 目标资源。 然后，您可以根据 **[!UICONTROL email]** 您的需 **[!UICONTROL Join definition]** 要，在部分或任何其他复合合并关键项中映射。

   ![](assets/optin_eventcreate_join.png)

   如果您需要使用服务，请添加 **[!UICONTROL Service]** 目标资源并在字段上 **[!UICONTROL serviceName]** 映射。 有关详细信息，请参阅 。

1. 在下 **[!UICONTROL Profile]** 拉列表 **[!UICONTROL Targeting enrichment]** 中选择作为。
1. 单击 **[!UICONTROL Publish]** 以发布事件。

事件准备好了。 您现在可以设计电子邮件模板。 此模板必须包含指向之前创建的 **CONFIRMATION** 登陆页的链接。 有关此方面的详细信息，请 [参阅设计确认消息](#design-the-confirmation-message)。

### 创建类型学 {#create-the-typology-rule}

您需要通过复 [制现成](../../sending/using/about-typology-rules.md)的字体创建特定的字体。 类型学允许向尚未确认其协议且仍在块列表中的用户档案发送消息。 默认情况下，排版排除选择退出（即在块列表中）用户档案。 要创建此类型，请按照以下步骤操作：

1. 从Adobe Campaign标志中，选择 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** 并单击 **[!UICONTROL Typologies]**。
1. 重复开箱即用的排版 **[!UICONTROL Transactional message on profile (mcTypologyProfile)]**。
1. 确认复制后，编辑新的排版并输入标 **签TYPOLOGY_用户档案**。
1. 删除块 **列表上的地址** 。
1. 单击 **[!UICONTROL Save]**.

此类型现在可与确认电子邮件关联。

### 设计确认消息 {#design-the-confirmation-message}

确认电子邮件是基于之前创建的事务性消息的事件。 请按照以下步骤创建此消息：

1. 从Adobe Campaign标志中，选择 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** 并单击 **[!UICONTROL Transactional messages]**。
1. 编辑确认 **电子邮** 件模板并对其进行个性化。 您可以上传现有内容或使用现成模板。
1. 添加指向确认 **登陆页** 的链接，然后 **[!UICONTROL Confirm]** 单击以保存修改。

   ![](assets/optin_email_selectlp.png)

1. 编辑电子邮件模板属性。 在> **[!UICONTROL Advanced parameters]** 部 **[!UICONTROL Preparation]** 分中，选择 **之前创建的** TYPOLOGY_用户档案类型。
1. 保存并发布事务性消息。

## 第3步： 创建客户获取登陆页 {#step-3--create-the-acquisition-landing-page}

您必须创建初始客户获取登陆页: 此选择加入表单将发布在您的网站上。

要创建并配置此登陆页，您需要：

1. 根据模 [板设计](../../channels/using/getting-started-with-landing-pages.md) 一个新的 **[!UICONTROL Profile acquisition (acquisition)]** 登陆页。 输入标签“**ACQUISITION**”。
1. 编辑登陆页属性： 在> **[!UICONTROL Job]** 部 **[!UICONTROL Additional data]** 分，单击并 **[!UICONTROL Add an element]** 输入以下上下文路径：

   /context/用户档案/blockList

   并将值设置为 **true**。

   这是强制添加到块列表并避免向未确认其协议的访客发送消息的必备选项。 确认登陆页的验证将在确认后将此字段设 **置为** false。 有关此方面的详细信息，请 [参阅步骤1: 创建确认登陆页](#step-1--create-the-confirmation-landing-page)。

1. 在> **[!UICONTROL Job]** 部 **[!UICONTROL Specific actions]** 分，选择选项 **[!UICONTROL Start sending messages]**。
1. 在关联的下拉列表中，选择您创 **建的** CONFIRM事务性消息模板。

   ![](assets/optin_acquisition_startoption.png)

1. 根据您的品牌和您需要获取的登陆页，自定义客户内容。 您可以显示个性化数据，并将确认按钮的标签更改 **为确认我的订阅** ，例如。

   ![](assets/optin_acquisition_page1.png)

1. 自定义确认页面，通知新订户他需要验证订阅。

   ![](assets/optin_acquisition_page2.png)

1. [测试和发布](../../channels/using/testing-publishing-landing-page.md) 登陆页。

多次加入机制现已配置。 您可以从此登陆页的公共URL开始，从头到尾运行并测试该过 **[!UICONTROL ACQUISITION]** 程。 此URL显示在登陆页仪表板中。
