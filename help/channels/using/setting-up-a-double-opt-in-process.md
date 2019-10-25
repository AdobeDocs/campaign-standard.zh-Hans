---
title: 设置双重加入流程
seo-title: 设置双重加入流程
description: 设置双重加入流程
seo-description: 按照以下步骤，使用Adobe Campaign中的登录页面设置双重选择加入流程。
page-status-flag: 从未激活
uuid: 23e6c4c2-e2c7-472f-b616-36a95225ac1d
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 频道
content-type: 参考
topic-tags: 登陆页面
discoiquuid: 1a24504e-7f9d-4297-b39e-c5f085b0f388
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# 设置双重加入流程{#setting-up-a-double-opt-in-process}

## 关于双选 {#about-double-opt-in}

双选择加入机制是发送电子邮件的最佳实践。 它可以保护平台免受错误或无效电子邮件地址、垃圾邮件程序的攻击，并防止可能的垃圾邮件投诉。

其原则是先发送电子邮件确认访客的协议，然后再将其作为“配置文件”存储到您的Campaign数据库中：访客填写在线登录页面，然后收到电子邮件，必须单击确认链接才能完成订阅。

![](assets/optin_mechanism.png)

要设置此设置，您需要：

1. 创建并发布登录页面，以便访客可以注册和订阅。 此登录页面可从网站访问。 填写并提交此登录页面的访客将存储在数据库中，但“列入黑名单”，以便在最终验证之前不会收到任何通信(请参阅管理 [Campaign中的黑名单](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md))。
1. 自动创建并发送包含确认链接的加入电子邮件。 此电子邮件将针对提交登录页面的人群。 它将基于电子邮件模板，该模板允许以“选择退出”配置文件为目标。
1. 重定向到确认登陆页面。 此最终登录页面将提出确认按钮：访客必须点击它。 您可以设计一封欢迎电子邮件，在确认完成后发送，例如，在电子邮件中为新收件人添加特价优惠。

这些步骤必须按特定顺序在Adobe Campaign中设置，才能正确启用所有参数。

## 第1步：创建确认登陆页面 {#step-1--create-the-confirmation-landing-page}

设置双选择加入机制的过程从创建确认登录页面开始：当访客点击确认电子邮件以进行注册时，将显示此页面。

要创建并配置此登录页面，您需要：

1. 根据模 [板设计新的登录](../../channels/using/about-landing-pages.md) 页 **[!UICONTROL Profile acquisition (acquisition)]** 面。 输入标签“**CONFIRMATION**”。

   如果需要使用 [服务](../../audiences/using/about-subscriptions.md)，您还可以使用模 **[!UICONTROL Subscription (sub)]** 板。

1. 编辑登陆页面属性，在部 **[!UICONTROL Access and loading]** 分中，取消选择选项， **[!UICONTROL Authorize unidentified visitors]**&#x200B;选择 **[!UICONTROL Preload visitor data]** （此选项不是必需的）。

   ![](assets/optin_confirmlp_param.png)

1. 在 **[!UICONTROL Job]** &gt;部 **[!UICONTROL Additional data]** 分中，单 **[!UICONTROL Add an element]** 击并输入以下上下文路径：

   /context/profile/blackList

   将该值设置为 **false** ，然后单击 **[!UICONTROL Add]**。

   ![](assets/optin_confirmlp_newelement.png)

   为了能够发送电子邮件，此上下文会删除黑名单字段。 我们稍后会看到，第一个登录页面在确认前将此字段设置为 **true** ，以防止向未确认的配置文件发送电子邮件。 有关此方面的详细信息，请参 [阅步骤3:创建客户获取登陆页面](#step-3--create-the-acquisition-landing-page)。

1. 自定义登录页面的内容：例如，您可以显示个性化数据并将确认按钮的标签更改为“单击此处确认我的订阅”。

   ![](assets/optin_confirmlp_design.png)

1. 调整确认页面的内容，以通知您的订阅者他们已注册。

   ![](assets/optin_confimlp_page2.png)

1. [测试并发布登陆页](../../channels/using/sharing-a-landing-page.md) 。

## 第2步：创建确认电子邮件 {#step-2--create-the-confirmation-email}

创建确认登录页面后，您可以设计确认电子邮件：此电子邮件将自动发送给验证客户获取登录页面的每位访客。 此验证被视为事件，而电子邮件是一条交易消息，它链接到特定的排版规则，允许针对选择退出人群。

创建这些元素的步骤如下所述。 您需要在创建客户赢取登陆页面之前遵循这些步骤，因为此电子邮件模板将在其中引用。

### 创建活动 {#create-the-event}

确认电子邮件是一 [条事务消息](../../channels/using/about-transactional-messaging.md) ，当它对事件作出反应时：表单的验证。 必须首先创建活动，然后创建事务性消息的模板。

1. 从&gt; **[!UICONTROL Marketing plans]** &gt;菜单创建活动， **[!UICONTROL Transactional messages]** 可从Adobe Campaign徽标访问该活动，然后输入标签“ **[!UICONTROL Event configuration]** 确认&#x200B;****”。
1. 选择定 **[!UICONTROL Profile]** 位维并单击 **[!UICONTROL Create]**。

   ![](assets/optin_eventcreate.png)

1. 在部分 **[!UICONTROL Fields]** 中，单击并 **[!UICONTROL Create element]** 在数据 **[!UICONTROL email]** 结构中添加以启用协调。
1. 在部分 **[!UICONTROL Enrichment]** 中，单击并 **[!UICONTROL Create element]** 选择目标 **[!UICONTROL Profile]** 资源。 然后，您可以根据需 **[!UICONTROL email]** 要在部分中的字 **[!UICONTROL Join definition]** 段或任何其他复合对帐密钥上进行映射。

   ![](assets/optin_eventcreate_join.png)

   如果需要使用服务，请添加目 **[!UICONTROL Service]** 标资源并在字段上映射 **[!UICONTROL serviceName]** 图。 有关此问题的详细信息，请参见。

1. 在下 **[!UICONTROL Profile]** 拉列 **[!UICONTROL Targeting enrichment]** 表中选择作为。
1. 单击 **[!UICONTROL Publish]** 以发布活动。

活动已准备就绪。 您现在可以设计电子邮件模板。 此模板必须包含指向之前创建的 **CONFIRMATION** 登陆页面的链接。 有关此问题的详细信息，请参 [阅设计确认消息](#design-the-confirmation-message)。

### 创建排版规则 {#create-the-typology-rule}

您需要通过复制现成 [的排版规则](../../administration/using/about-typology-rules.md)，来创建特定的排版规则。 此规则允许向尚未确认其协议且仍被列入黑名单的配置文件发送消息。 默认情况下，排版规则不包括选择退出（即列入黑名单）的配置文件。 要创建此排版规则，请按照以下步骤操作：

1. 从Adobe Campaign徽标中，选择 **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt;并 **[!UICONTROL Typologies]** 单击 **[!UICONTROL Typologies]**。
1. 复制开箱即用的类型学 **[!UICONTROL Transactional message on profile (mcTypologyProfile)]**。
1. 确认复制后，编辑新的排版并输入标签 **TYPOLOGY_PROFILE**。
1. 删除列入黑 **名单的地址** 规则。
1. Click **[!UICONTROL Save]**.

此类型现在可与确认电子邮件关联。

### 设计确认消息 {#design-the-confirmation-message}

确认电子邮件是基于之前创建的活动的事务性消息。 请按照以下步骤创建此消息：

1. 从Adobe Campaign徽标中，选择 **[!UICONTROL Marketing plans]** &gt;并 **[!UICONTROL Transactional messages]** 单击 **[!UICONTROL Transactional messages]**。
1. 编辑CONFIRM **电子邮件模** 板并对其进行个性化设置。 您可以上传现有内容或使用现成的模板。
1. 添加指向确认登 **陆页** ，然后单击 **[!UICONTROL Confirm]** 以保存修改。

   ![](assets/optin_email_selectlp.png)

1. 编辑电子邮件模板属性。 在 **[!UICONTROL Advanced parameters]** &gt;部 **[!UICONTROL Preparation]** 分中，选择 **之前创建的TYPOLOGY_PROFILE** 类型。
1. 保存并发布交易消息。

## 第3步：创建客户赢取登录页 {#step-3--create-the-acquisition-landing-page}

您必须创建初始客户获取登录页面：此选择加入表单将发布在您的网站上。

要创建并配置此登录页面，您需要：

1. 根据模 [板设计新的登录](../../channels/using/about-landing-pages.md) 页 **[!UICONTROL Profile acquisition (acquisition)]** 面。 输入标签“**ACQUISITION**”。
1. 编辑登陆页面属性：在 **[!UICONTROL Job]** &gt;部 **[!UICONTROL Additional data]** 分中，单击并 **[!UICONTROL Add an element]** 输入以下上下文路径：

   /context/profile/blackList

   并将值设置为 **true**。

   这是强制要求强制列入黑名单，并避免向未确认同意的访客发送消息。 确认登陆页面的验证将在确认后将此字段设 **置为** false。 有关此方面的详细信息，请参 [阅步骤1:创建确认登陆页面](#step-1--create-the-confirmation-landing-page)。

1. 在 **[!UICONTROL Job]** &gt;部 **[!UICONTROL Specific actions]** 分中，选择选项 **[!UICONTROL Start sending messages]**。
1. 在关联的下拉列表中，选择您创建的 **CONFIRM** Transactional Message模板。

   ![](assets/optin_acquisition_startoption.png)

1. 根据您的品牌和您需要获取的数据自定义登录页面的内容。 例如，您可以显示个性化数据并将确认按钮的标签更 **改为确认我的订阅** 。

   ![](assets/optin_acquisition_page1.png)

1. 自定义确认页面以通知新订阅者他需要验证其订阅。

   ![](assets/optin_acquisition_page2.png)

1. [测试并发布登陆页](../../channels/using/sharing-a-landing-page.md) 。

现在配置了双选入机制。 您可以从此登录页面的公共URL开始，从头到尾运行并测 **[!UICONTROL ACQUISITION]** 试过程。 此URL显示在登陆页面功能板中。
