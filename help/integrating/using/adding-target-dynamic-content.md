---
solution: Campaign Standard
product: campaign
title: 添加 Target 动态内容
description: 了解如何将Adobe Target动态内容添加到您的某个Adobe Campaign投放中。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
translation-type: tm+mt
source-git-commit: 3672f0bc4ebc551c4eb34660a3a55d44fa726f1a
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 5%

---


# 添加 Target 动态内容{#adding-target-dynamic-content}

通过Adobe Target集成，可以将动态图像添加到投放中，以根据体验个性化您的内容。

在编辑电子邮件时，您可以插入Adobe Target中的动态图像，该动态图像会因收件人而异。

在Adobe Campaign中访问图像之前，必须先在Adobe Target中执行以下任务:

* 创建一个或多个[重定向优惠](https://docs.adobe.com/content/help/en/target/using/experiences/offers/offer-redirect.html)，您必须在其中指定要使用的图像的URL。
* 创建一个或多个[受众](https://docs.adobe.com/content/help/en/target/using/audiences/create-audiences/audiences.html)，以定义活动的目标。
* 创建一个[基于表单的体验编辑器](https://docs.adobe.com/content/help/en/target/using/experiences/form-experience-composer.html)活动，您必须在其中选择一个rawbox并指定多个体验，具体取决于创建的重定向优惠的数量。 对于每个体验，您必须选择创建的重定向优惠之一。
* 使用Adobe Campaign中的信息创建区段以指定体验。 要使用优惠选择规则中的Adobe Campaign数据，必须在Adobe Target的rawbox中指定数据。

1. 创建电子邮件投放。
1. 编辑电子邮件或登陆页的内容时，转到图像块，然后通过上下文菜单选择&#x200B;**[!UICONTROL Dynamic image from Adobe Target]**。

   ![](assets/tar_insert_dynamic_image.png)

1. 选择默认情况下将在电子邮件中显示的图像。 您可以直接指定图像URL或选择通过[Assets](../../integrating/using/working-with-campaign-and-assets-core-service.md)共享的图像。

   集成仅支持静态图像。 其余内容不可自定义。

1. 输入在Adobe Target中指定的rawbox的名称。
1. 如果您在Adobe Target中的设置中使用“企业”权限，请在此字段中添加相应的属性。 了解有关[本页](https://docs.adobe.com/content/help/en/target/using/administer/manage-users/enterprise/properties-overview.html)中的目标 Enterprise权限的更多信息。 如果您未在目标中使用企业权限，则此字段是可选字段，不是必填字段。
1. 在&#x200B;**[!UICONTROL Additional decision parameters]**&#x200B;中，指定在Adobe Target区段中定义的字段与Adobe Campaign字段之间的映射。

   必须使用的Adobe Campaign字段必须已在rawbox中指定。 在此，我们将根据收件人的性别定义不同的体验。

   ![](assets/tar_additional_decisionning_parameters.png)

1. 预览您的电子邮件以查看在选择不同用户档案时，插入的图像是否会根据在Adobe Target活动和Adobe Campaign中指定的参数而发生更改。

现在可以发送包含动态图像的投放。 结果可在Adobe Target找到。

**相关主题：**

* [Adobe Target门户](https://docs.adobe.com/content/help/en/target/using/integrate/campaign-and-target.html)
* [关于电子邮件内容设计](../../designing/using/designing-content-in-adobe-campaign.md)
* [以实时视频方式个性化电子邮件](https://helpx.adobe.com/cn/marketing-cloud/how-to/email-marketing.html) 图像

