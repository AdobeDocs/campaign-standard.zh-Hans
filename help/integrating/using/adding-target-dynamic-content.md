---
title: 添加Target动态内容
seo-title: 添加Target动态内容
description: 添加Target动态内容
seo-description: 了解如何在您的Adobe Campaign交付中添加Adobe Target动态内容。
page-status-flag: 从未激活
uuid: b3cc045f-7924-480e-8c61-8246510f3adb
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 集成
content-type: 参考
topic-tags: 使用系列活动和目标
discoiquuid: 45ddf7b7-98f7-4fdd-bb4a-49ec8490e877
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ea825afe573959d95d0f7f3f6e79dd38ac5a678a

---


# 添加Target动态内容{#adding-target-dynamic-content}

通过Adobe target集成，可以将动态图像添加到交付中，以根据体验个性化您的内容。

在编辑电子邮件时，您可以插入Adobe Target中的动态图像，该动态图像将因收件人而异。

在Adobe Campaign中访问图像之前，必须先在Adobe target中执行以下任务：

* 创建一个或多个 [重定向选件](https://docs.adobe.com/content/help/en/target/using/experiences/offers/offer-redirect.html)，您必须在其中指定要使用的图像的URL。
* 创建一个或多 [个受众](https://marketing.adobe.com/resources/help/en_US/target/ov/c_about_segments.html)，以定义活动的目标。
* 创建基 [于表单的体验编写器活动](https://marketing.adobe.com/resources/help/en_US/target/target/t_form_experience_composer.html) ，您必须在其中选择一个rawbox并指定多个体验，具体取决于创建的重定向选件的数量。 对于每个体验，您必须选择其中一个已创建的重定向选件。
* 使用Adobe Campaign中的信息创建区段以指定体验。 要在选件的选择规则中使用Adobe Campaign中的数据，您必须在Adobe Target的rawbox中指定数据。

1. 创建电子邮件分发。
1. 编辑电子邮件或登陆页面的内容时，请转到图像块，然后通过上下文菜 **[!UICONTROL Dynamic image from Adobe Target]** 单进行选择。

   ![](assets/tar_insert_dynamic_image.png)

1. 选择默认情况下将在电子邮件中显示的图像。 您可以直接指定图像URL或选择通过资产共享的 [图像](../../integrating/using/working-with-campaign-and-assets-core-service.md)。

   该集成仅支持静态图像。 其余内容不可自定义。

1. 输入在Adobe Target中指定的rawbox的名称。
1. 如果您在Adobe target中的设置中使用Enterprise权限，请在此字段中添加相应的属性。 在本页中进一步了解Target Enterprise [权限](https://marketing.adobe.com/resources/help/en_US/target/target/properties-overview.html)。 如果您未在Target中使用Enterprise权限，则此字段为可选字段，而非必需字段。
1. 在 **[!UICONTROL Additional decision parameters]**&#x200B;中，指定Adobe Target区段中定义的字段与Adobe Campaign字段之间的映射。

   在rawbox中必须已指定使用的Adobe Campaign字段。 在此，我们将根据受助者的性别定义不同的体验。

   ![](assets/tar_additional_decisionning_parameters.png)

1. 预览您的电子邮件，查看在选择不同的配置文件时，图像是否插入了更改，具体取决于在Adobe Target活动和Adobe Campaign中指定的参数。

现在可以发送包含动态图像的传送。 其结果可在Adobe Target中找到。

**相关主题：**

* [Adobe Target门户](https://marketing.adobe.com/resources/help/en_US/target/a4t/c_campaign_and_target.html)
* [关于电子邮件内容设计](../../designing/using/overview.md)
* [实时视频中个性化电子邮件图像](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html)

