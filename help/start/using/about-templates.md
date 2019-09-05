---
title: 关于模板
seo-title: 关于模板
description: 关于模板
seo-description: “Adobe Campaign模板允许您根据需要预配置参数：模板可能包含营销活动的完整或部分配置，以简化非技术最终用户的Adobe Campaign使用”。
page-status-flag: 从未激活
uuid: 018534b6-61a3-433e-bb60-49883c8 b9386
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: 管理模板
discoiquuid: 95218ebe-5430-42a2-b900-1dadbutton92 d99
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 8e2766bb9fef619142d3ee59cb8aa8ed20424a3f

---


# 关于模板{#about-templates}

## 营销活动模板 {#marketing-activity-templates}

当您创建新的营销活动时，向导中的第一个屏幕会要求您选择类型或模板。模板允许您根据需要预配置某些参数。模板可能包含营销活动的完整或部分配置。模板管理由职能管理员执行。

最终用户具有简化的界面。创建新的营销活动时，您只需选择要使用的模板。无需担心任何技术配置。这已经由模板中的功能管理员预先配置。

例如，对于电子邮件模板，您可以预填HTML内容、受众以及交付的任何其他参数：计划、测试配置文件、交付的一般属性、高级参数等。这允许您在创建新活动时节省时间。

![](assets/template_1.png)

对于每种类型的营销活动，只需很少的配置即可提供一个或多个现成的模板。这些现成的模板无法修改或删除。

模板可用于以下营销活动：

* Programs
* Campaign
* 电子邮件交付
* SMS交付
* 推送通知
* 登陆页面
* 工作流
* 服务业
* Import
* 交易消息

这些模板是从 **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** 屏幕管理的。

>[!NOTE]
>
>可以在电子邮件或登录页面模板中预配置品牌配置。有关更多信息，请参阅 [品牌](../../administration/using/branding.md) 部分。

## 内容模板 {#content-templates}

可从高级菜单的 **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]** 屏幕访问HTML内容 [模板](../../start/using/interface-description.md#advanced-menu)。您可以从此处管理登陆页面内容模板、电子邮件内容模板和片段。

![](assets/content_templates_list.png)

现成的内容模板是只读的。要编辑其中一个，您必须先复制它。

您可以创建新模板或片段，并定义自己的内容。有关此操作的详细信息，请参阅 [创建内容模板](../../start/using/about-templates.md#creating-a-content-template) 和 [创建内容片段](../../designing/using/defining-the-email-structure.md#creating-a-content-fragment)。

使用电子邮件设计器编辑内容时，您还可以将内容保存为片段或模板，从而创建内容模板。有关此操作的详细信息，请参阅 [将内容保存为模板](../../start/using/about-templates.md#saving-content-as-template) 和 [将内容保存为片段](../../designing/using/defining-the-email-structure.md#saving-content-as-a-fragment)。

### 现成的电子邮件内容模板 {#email-content-templates}

您可以管理 **[!UICONTROL Templates]**[电子邮件设计器](../../designing/using/about-email-content-design.md#about-the-email-designer) 主页选项卡中提供的HTML内容。

现成的电子邮件内容模板包括18个移动优化版面以及由Behance艺术家设计的四个一流的响应式模板。它们对应于最新的用户服务，例如客户欢迎消息、新闻稿和重新互动电子邮件等。您可以轻松使用品牌内容自定义它们，从而轻松地从头开始设计电子邮件。

![](assets/content_templates.png)

**相关主题：**

* 了解如何在此视频中个性化内容模板 [](https://helpx.adobe.com/campaign/kt/acs/using/acs-email_content_templates-feature-video-use.html)。
* 有关编辑内容的更多信息，请参阅 [关于电子邮件内容设计](../../designing/using/about-email-content-design.md)。

### 创建内容模板 {#creating-a-content-template}

您可以创建自己的内容模板，以根据需要多次使用它们。

以下示例演示如何创建电子邮件内容模板。

1. 转到 **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]** 并单击 **[!UICONTROL Create]**。
1. 单击电子邮件标签以访问电子邮件设计器 **[!UICONTROL Properties]** 的选项卡。
1. 指定可识别的标签并选择以下参数以在电子邮件中使用此模板：

   * 选择 **[!UICONTROL Shared]** 或 **[!UICONTROL Delivery]** 从下 **[!UICONTROL Content type]** 拉列表中。
   * **[!UICONTROL Template]** 从 **[!UICONTROL HTML type]** 下拉列表中进行选择。
   ![](assets/email_designer_create-template.png)

1. 如果需要，您可以设置将用作模板缩略图的图像。从模板属性 **[!UICONTROL Thumbnail]** 的选项卡中选择它。

   ![](assets/email_designer_create-template_thumbnail.png)

   此缩略图将显示在 **[!UICONTROL Templates]**[电子邮件设计器](../../designing/using/about-email-content-design.md#about-the-email-designer) 主页的选项卡中。

1. 关闭 **[!UICONTROL Properties]** 选项卡以返回主工作区。
1. 添加可根据需要自定义的结构组件和内容组件。
   >[!NOTE]
   >
   > 您不能在内容模板中插入个性化字段或条件内容。
1. 编辑后，保存模板。

此模板现在可用于使用电子邮件设计器构建的任何电子邮件。从 **[!UICONTROL Templates]**[电子邮件设计器](../../designing/using/about-email-content-design.md#about-the-email-designer) 主页的选项卡中选择它。

![](assets/content_template_new.png)

### 将内容保存为模板 {#saving-content-as-template}

使用电子邮件设计器编辑电子邮件时，您可以直接将该电子邮件的内容保存为模板。

<!--[!CAUTION]
>
>You cannot save as template a structure containing personalization fields or dynamic content.-->

1. 从 **[!UICONTROL Save as template]** 电子邮件设计器主工具栏中进行选择。

   ![](assets/email_designer_save-as-template.png)

1. 根据需要添加标签和说明，然后单击 **[!UICONTROL Save]**。

   ![](assets/email_designer_save-as-template_creation.png)

1. 要查找刚刚创建的模板，请转到 **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]**。

1. 要使用新模板，请从 **[!UICONTROL Templates]**[电子邮件设计器](../../designing/using/about-email-content-design.md#about-the-email-designer) 主页的选项卡中选择该模板。

   ![](assets/content_template_new.png)

