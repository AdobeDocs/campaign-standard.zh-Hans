---
solution: Campaign Standard
product: campaign
title: 关于 Campaign-Experience Manager 集成
description: 借助Adobe Experience Manager集成，您可以直接在AEM中创建内容，然后在Adobe Campaign中使用。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: 触发器
role: 数据架构师
level: 中间
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 1%

---


# 关于 Campaign-Experience Manager 集成{#integrating-with-experience-manager}

Adobe Campaign Standard和Adobe Experience Manager之间的这一集成允许您在Adobe Campaign电子邮件中使用Adobe Experience Manager中创建的内容。

因此，您可以充分利用Adobe Experience Manager内容编辑功能以及Adobe Campaign的投放和数据管理功能。 请注意，无法对从Adobe Experience Manager导入的内容执行A/B测试。

Adobe Campaign Standard与Adobe Experience Manager 6.1、6.2、6.3、6.4和6.5兼容。以下部分概述了您可以执行的操作。 有关详细信息，请参阅专门用于[configuration](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html)和集成的[use](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/aem-adobe-campaign/campaign.html)的部分。

>[!NOTE]
>
> Adobe Campaign Standard模板在Adobe Experience Manager 6.5中不再可用。

## 有关如何使用活动-Experience Manager集成{#tips-aem}的提示

* **了解要与集成一起使用的模板**

   由于电子邮件模板可在Adobe Experience Manager中编辑，因此在Adobe Experience Manager中编辑任何模板可能会更简单。 但某些模板并不容易适应。 此集成不建议使用特定于一位客户的个性化模板，应直接在Adobe Campaign Standard中编辑。

   有关模板的详细信息，请参阅此[页面](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/templates/templates.html)。

* **确保在实施过程中配置了Externalizer**

   在为Adobe Campaign Standard实施Experience Manager时配置Externalizer可以将资源路径转换为URL。 这样，您就可以在页面上显示图像。 如果Externalizer配置不正确，则您的电子邮件将包含损坏的图像。

   要了解如何配置Externalizer，请参阅此[页面](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/externalizer.html)。

* **整理您的电子邮件模板，避免误用。**

   保持模板条理井然，可确保适当的模板位于适当的文件夹中，并且不会误选错误的模板。 在实施过程中，应创建路径以在正确的位置保存模板。

   有关模板的详细信息，请参阅此[页面](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/templates/templates.html#template-availability)。

* **开箱即用的组件快速入门。**

   Adobe Experience Manager for Adobe Campaign Standard中的现成组件可以帮助您在模板不复杂时快速入门。
Experience Manager中有七个现成的组件，您可以使用以下工具进行开始:

   * 标题
   * 图像
   * 链接
   * Scene7图像模板
   * 目标引用
   * 文本和图像
   * 文本与个性化

* **电子邮件的HTML与Web的HTML不同**

   请务必了解，您不能将Web内容中使用的相同组件用于电子邮件模板。 使用开箱即用的组件可确保您的组件与电子邮件兼容。

* **取消链接模板中的内容，并一次又一次地重复使用它们。**

   在Campaign Standard中设置电子邮件并选择Experience Manager模板时，您只能选择尚未链接到其他活动的电子邮件。 否则，如果您在Adobe Experience Manager中为一个活动更改内容并进行刷新，您可能会无意中影响另一个活动中的内容。
要避免这种情况，在您使用完模板后，可以取消其链接以再次使用它。 您只需选择模板并单击**[!UICONTROL Delete the link with Adobe Experience Manager content]**。

* **使用Adobe Experience Manager为Adobe Campaign Standard创建各种电子邮件。**

   此集成允许您通过分段将一封电子邮件轻松转换为多个版本。
要了解如何在Adobe Experience Manager中设置分段以及如何创建包含目标内容的电子邮件，请参阅此[页面](https://docs.adobe.com/help/en/experience-manager-65/authoring/aem-adobe-campaign/target-adobe-campaign.html#setting-up-segmentation-in-aem)。

* **要成功同步，Experience Manager中的区段名称必须与活动中的区段名称完全匹配。**