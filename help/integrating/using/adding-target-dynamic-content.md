---
title: 添加 Target 动态内容
description: 了解如何在一个Adobe Target投放中添加Adobe Campaign动态内容。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 7dfbd89f-877e-4598-bfe3-d743bb31ae9e
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 5%

---

# 添加 Target 动态内容{#adding-target-dynamic-content}

通过Adobe Target集成，可以将动态图像添加到投放中，以根据体验对内容进行个性化。

在编辑电子邮件时，您可以从Adobe Target插入动态图像，该动态图像将根据收件人进行更改。

在Adobe Campaign中访问图像之前，必须首先在Adobe Target中执行以下任务：

* 创建一个或多个 [重定向选件](https://experienceleague.adobe.com/docs/target/using/experiences/offers/offer-redirect.html)，您必须在该对话框中指定要使用的图像的URL。
* 创建一个或多个 [受众](https://experienceleague.adobe.com/docs/target/using/audiences/create-audiences/audiences.html)，以定义活动的目标。
* 创建 [基于表单的体验编辑器](https://experienceleague.adobe.com/docs/target/using/experiences/form-experience-composer.html) 活动，您必须在该活动中选择一个rawbox并指定多个体验，具体取决于创建的重定向选件数量。 对于每个体验，您必须选择已创建的重定向选件之一。
* 使用Adobe Campaign中的信息创建区段以指定体验。 要在选件的选择规则中使用来自Adobe Campaign的数据，您必须在Adobe Target的rawbox中指定数据。

1. 创建电子邮件投放.
1. 编辑电子邮件或登陆页面的内容时，转到图像块，然后选择 **[!UICONTROL Dynamic image from Adobe Target]** 通过上下文菜单。

   ![](assets/tar_insert_dynamic_image.png)

1. 选择默认显示在电子邮件中的图像。 您可以直接指定图像URL，也可以选择通过以下方式共享的图像 [资产](../../integrating/using/working-with-campaign-and-assets-core-service.md).

   该集成仅支持静态图像。 内容的其余部分不可自定义。

1. 输入Adobe Target中指定的rawbox的名称。
1. 如果您在Adobe Target的设置中使用企业权限，请在此字段中添加相应的资产。 在中了解有关Target企业权限的更多信息 [此页面](https://experienceleague.adobe.com/docs/target/using/administer/manage-users/enterprise/properties-overview.html). 此字段是可选字段，如果您未在Target中使用企业权限，则它是非必填字段。
1. 在 **[!UICONTROL Additional decision parameters]**，指定Adobe Target区段中定义的字段与Adobe Campaign字段之间的映射。

   使用的Adobe Campaign字段必须在rawbox中指定。 在此示例中，根据收件人的性别定义不同的体验。

   ![](assets/tar_additional_decisionning_parameters.png)

1. 预览您的电子邮件，以查看在选择不同的用户档案时，插入的图像是否根据Adobe Target活动和Adobe Campaign中指定的参数而发生更改。

现在可以发送包含动态图像的投放。 其结果可以在Adobe Target中找到。

**相关主题：**

* [Adobe Target门户](https://experienceleague.adobe.com/docs/target/using/integrate/campaign-and-target.html)
* [关于电子邮件内容设计](../../designing/using/designing-content-in-adobe-campaign.md)
* [实时个性化电子邮件图像](https://helpx.adobe.com/cn/marketing-cloud/how-to/email-marketing.html) 视频
