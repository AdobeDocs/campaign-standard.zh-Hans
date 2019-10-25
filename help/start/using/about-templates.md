---
title: 关于模板
seo-title: 关于模板
description: 关于模板
seo-description: “Adobe Campaign模板允许您根据自己的需求预配置参数：模板可能包含营销活动的完整或部分配置，以简化非技术最终用户的Adobe Campaign使用。”
page-status-flag: 从未激活
uuid: 018534b6-61a3-433e-bb60-49883c8b9386
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 开始
content-type: 参考
topic-tags: 管理模板
discoiquuid: 95218ebe-5430-42a2-b900-1dadbbc92d99
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# 关于模板{#about-templates}

## 营销活动模板 {#marketing-activity-templates}

创建新的营销活动时，向导中的第一个屏幕会要求您选择类型或模板。 模板允许您根据需要预配置某些参数。 模板可能包含营销活动的完整或部分配置。 模板管理由职能管理员执行。

最终用户的界面已简化。 创建新营销活动时，您只需选择要使用的模板。 无需担心任何技术配置。 该模板已由职能管理员在模板中预配置。

例如，对于电子邮件模板，您可以预填充HTML内容、受众和您分发的任何其他参数：计划、测试配置文件、交付的常规属性、高级参数等。 这样，您就可以在创建新活动时节省时间。

![](assets/template_1.png)

对于每种类型的营销活动，可以使用一个或多个现成模板，只需极少的配置。 无法修改或删除这些现成模板。

模板可用于以下营销活动：

* 计划
* 营销活动
* 电子邮件发送
* SMS交付
* 推送通知
* 登陆页面
* 工作流
* 服务
* 导入
* 交易消息

这些模板可从 **[!UICONTROL Resources]** &gt;屏幕 **[!UICONTROL Templates]** 管理。

>[!NOTE]
>
>品牌配置可以在电子邮件或登录页面模板中预配置。 有关详细信息，请参阅品 [牌推广](../../administration/using/branding.md) 部分。

## 内容模板 {#content-templates}

HTML内容模板可从“高级”菜单 **[!UICONTROL Resources]** 的&gt; **[!UICONTROL Content templates & fragments]** 屏幕 [访问](../../start/using/interface-description.md#advanced-menu)。 您可以从中管理登陆页面内容模板、电子邮件内容模板以及片段。

![](assets/content_templates_list.png)

现成内容模板为只读模板。 要编辑其中一个模板，您必须首先复制所需的模板。

您可以创建新模板或片段，并定义您自己的内容。 有关此内容的详细信息，请 [参阅创建内容模板](#creating-a-content-template)[和创建内容片段](../../designing/using/using-reusable-content.md#creating-a-content-fragment)。

在使用电子邮件设计器编辑内容时，您还可以通过将内容另存为片段或模板来创建内容模板。 有关详细信息，请参 [阅将内容另存为模板](#saving-content-as-template) , [将内容另存为片段](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment)。

### 开箱即用的电子邮件内容模板 {#email-content-templates}

您可以管理电子邮件设计器主页 **[!UICONTROL Templates]** 选项卡中提 [供的HTML内容](../../designing/using/overview.md) 。

现成的电子邮件内容模板包括十八个针对移动设备优化的布局和四个由Behance艺术家设计的一流响应式模板。 它们与最新的使用方式（如客户欢迎消息、新闻稿和重新参与电子邮件等）相对应。 您可以根据品牌内容轻松自定义这些内容，从而简化从头开始设计电子邮件的过程。

![](assets/content_templates.png)

**相关主题：**

* 了解如何在此视频中个性化 [内容模板](https://helpx.adobe.com/campaign/kt/acs/using/acs-email_content_templates-feature-video-use.html)。
* 有关编辑内容的详细信息，请参阅关于 [电子邮件内容设计](../../designing/using/overview.md)。

### Creating a content template {#creating-a-content-template}

您可以创建自己的内容模板，以根据需要多次使用它们。

以下示例演示如何创建电子邮件内容模板。

1. 转到 **[!UICONTROL Resources]** &gt;并 **[!UICONTROL Content templates & fragments]** 单击 **[!UICONTROL Create]**。
1. 单击电子邮件标签以访问电子 **[!UICONTROL Properties]** 邮件设计器的选项卡。
1. 指定可识别的标签，并选择以下参数以便能够在电子邮件中使用此模板：

   * 从 **[!UICONTROL Shared]** 下拉 **[!UICONTROL Delivery]** 列表 **[!UICONTROL Content type]** 中选择或。
   * 从下 **[!UICONTROL Template]** 拉列 **[!UICONTROL HTML type]** 表中进行选择。
   ![](assets/email_designer_create-template.png)

1. 如果需要，您可以设置一幅图像，该图像将用作模板的缩略图。 从模板属性的选 **[!UICONTROL Thumbnail]** 项卡中选择它。

   ![](assets/email_designer_create-template_thumbnail.png)

   此缩略图将显示在“电子邮 **[!UICONTROL Templates]** 件设计器”主 [页的选项卡中](../../designing/using/overview.md) 。

1. 关闭选 **[!UICONTROL Properties]** 项卡以返回到主工作区。
1. 添加结构组件和内容组件，您可以根据需要自定义这些组件和内容组件。
   >[!NOTE]
   >
   > 不能在内容模板中插入个性化字段或条件内容。
1. 编辑后，保存模板。

此模板现在可用于使用电子邮件设计器构建的任何电子邮件。 从“电子邮件设计 **[!UICONTROL Templates]** 器”主页的选 [项卡中选择](../../designing/using/overview.md) 。

![](assets/content_template_new.png)

### 将内容另存为模板 {#saving-content-as-template}

使用电子邮件设计器编辑电子邮件时，您可以直接将该电子邮件的内容另存为模板。

<!--[!CAUTION]
>
>You cannot save as template a structure containing personalization fields or dynamic content.-->

1. 从“电 **[!UICONTROL Save as template]** 子邮件设计器”主工具栏中进行选择。

   ![](assets/email_designer_save-as-template.png)

1. 根据需要添加标签和说明，然后单击 **[!UICONTROL Save]**。

   ![](assets/email_designer_save-as-template_creation.png)

1. 要查找您刚刚创建的模板，请转至 **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]**。

1. 要使用新模板，请从“电子邮件设计器”主 **[!UICONTROL Templates]** 页的选项卡 [中选择它](../../designing/using/overview.md) 。

   ![](assets/content_template_new.png)

