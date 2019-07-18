---
title: 添加Target动态内容
seo-title: 添加Target动态内容
description: 添加Target动态内容
seo-description: 了解如何在某个Adobe Campaign交付中添加Adobe Target动态内容。
page-status-flag: 从未激活
uuid: b3cc045f-7924-480e-8c61-8246510f3adb
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 集成
content-type: reference
topic-tags: 使用营销活动和目标
discoiquuid: 45ddf7b7-98f7-4fdd-bb4 a-49ec8490 e877
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Adding Target dynamic content{#adding-target-dynamic-content}

通过Adobe Target集成，可将动态图像添加到交付中，从而根据体验个性化您的内容。

编辑电子邮件时，您可以插入Adobe Target中的动态图像，该图像会根据收件人而改变。

在Adobe Campaign中访问图像之前，必须首先在Adobe Target中执行以下任务：

* Create one or several [redirect offers](https://marketing.adobe.com/resources/help/en_US/tnt/help/t_Creating_a_Redirect_Offer.html), in which you must specify the URL of the image you will be using.
* Create one or several [audiences](https://marketing.adobe.com/resources/help/en_US/target/ov/c_about_segments.html), to define the target of your activity.
* Create a [Form-based experience composer](https://marketing.adobe.com/resources/help/en_US/target/target/t_form_experience_composer.html) activity, in which you have to select a rawbox and specify several experiences, depending on the number of redirect offers created. 对于每个体验，您必须选择一个重新定向选件。
* 使用Adobe Campaign中的信息创建细分以指定体验。要在选件的选择规则中使用Adobe Campaign中的数据，您必须在Adobe Target的rawbox中指定数据。

1. 创建电子邮件分发。
1. When editing the content of an email or a landing page, go to an image block, then select **[!UICONTROL Dynamic image from Adobe Target]** via the contextual menu.

   ![](assets/tar_insert_dynamic_image.png)

1. 选择在电子邮件中默认显示的图像。You can directly specify the image URL or select an image shared via [Assets](../../integrating/using/working-with-campaign-and-assets-core-service.md).

   此集成仅支持静态图像。其余内容不可自定义。

1. 输入在Adobe Target中指定的rawbox的名称。
1. 如果在Adobe Target中的设置中使用企业权限，请在此字段中添加相应的属性。Learn more about Target Enterprise permissions in [this page](https://marketing.adobe.com/resources/help/en_US/target/target/properties-overview.html). 此字段为可选字段，如果您不在Target中使用Enterprise权限，则不需要此字段。
1. In **[!UICONTROL Additional decision parameters]**, specify the mapping between the fields defined in the Adobe Target segments and the Adobe Campaign fields.

   使用的Adobe Campaign字段必须在rawbox中指定。这里，我们将根据收件人的性别定义不同的体验。

   ![](assets/tar_additional_decisionning_parameters.png)

1. 预览您的电子邮件以查看在选择不同配置文件时，插入的图像会根据Adobe Target活动中指定的参数和Adobe Campaign中指定的参数而发生更改。

现在可以发送包含动态图像的传送。可在Adobe Target中找到其结果。

**相关主题：**

* [Adobe Target门户](https://marketing.adobe.com/resources/help/en_US/target/a4t/c_campaign_and_target.html)
* [关于电子邮件内容设计](../../designing/using/about-email-content-design.md)
* [在实时](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) 视频中个性化电子邮件图象

