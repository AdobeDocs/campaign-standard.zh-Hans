---
title: 关于 Campaign-Experience Manager 集成
description: 通过Adobe Experience manager集成，您可以直接在AEM中创建内容，然后在Adobe Campaign中使用它。
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5c1a540475b7d93c18c957243ee2a403b8154aa3

---


# 关于 Campaign-Experience Manager 集成{#integrating-with-experience-manager}

Adobe Campaign standard与Adobe Experience manager之间的这一集成允许您在Adobe Campaign电子邮件中使用Adobe Experience manager中创建的内容。

因此，您可以充分利用Adobe Experience manager内容编辑功能以及Adobe Campaign的交付和数据管理功能。 请注意，您无法对从Adobe Experience Manager导入的内容执行A/B测试。

Adobe Campaign Standard与Adobe Experience Manager 6.1、6.2、6.3、6.4和6.5兼容。以下各节概述了您可以执行的操作。 有关详细信息，请参阅专门用于配 [置](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html)[和集](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/aem-adobe-campaign/campaign.html) 成的使用。

>[!NOTE]
>
> Adobe Campaign standard模板不再在Adobe Experience Manager 6.5中可用。

## 关于如何使用Campaign-Experience manager集成的提示 {#tips-aem}

* **了解要与集成一起使用的模板**

   由于电子邮件模板可在Adobe Experience manager中编辑，因此在Adobe Experience manager中编辑任何模板看起来都更简单。 但某些模板并不容易容纳。 此集成不建议使用特定于一位客户的个性化模板，并应直接在Adobe Campaign standard中进行编辑。

   有关模板的详细信息，请参阅此 [页](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/templates/templates.html)。

* **确保在实施过程中配置了Externalizer**

   在实施Experience Manager for Adobe Campaign Standard时配置Externalizer，可以将资源路径转换为URL。 这允许您使图像在页面上可见。 如果Externalizer配置不正确，则电子邮件中将包含损坏的图像。

   要了解如何配置Externalizer，请参阅本 [页](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/externalizer.html)

* **组织电子邮件模板以避免误用。**

   保持模板有序可确保相应的模板位于相应的文件夹中，并且不会误选错误的模板。 在实施过程中，应创建路径以将模板保存到正确的位置。

   有关模板的详细信息，请参阅本 [页](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/templates/templates.html#template-availability)

* **开箱即用的组件快速入门。**

   Adobe Experience Manager for Adobe Campaign Standard中的现成组件可以帮助您在模板不复杂时快速入门。
Experience Manager中有七个现成的组件，您可以开始使用：
   1. 标题
   1. 图像
   1. 链接
   1. Scene7图像模板
   1. 目标引用
   1. 文本和图像
   1. 文本与个性化

* **电子邮件的HTML与Web的HTML不同**

   请务必了解，您不能将Web内容中使用的相同组件用于电子邮件模板。 使用现成组件可确保您的组件与电子邮件兼容。

* **将内容与模板取消链接，并反复重用它们。**

   在Campaign standard中设置电子邮件并选择Experience manager模板时，您只能选择尚未链接到其他营销活动的电子邮件。 否则，如果您在一个营销活动中更改Adobe Experience Manager中的内容并进行刷新，您可能会无意中影响另一个营销活动中的内容。
要避免这种情况，在您使用完模板后，可以取消其链接以再次使用它。 您只需选择模板并单击 **[!UICONTROL Delete the link with Adobe Experience Manager content]**。

* **使用Adobe Experience Manager为Adobe Campaign standard创建各种电子邮件。**

   通过此集成，您可以轻松地将一封电子邮件转换为具有分段的多个版本。
要了解如何在Adobe Experience Manager中设置细分以及如何创建包含目标内容的电子邮件，请参阅此 [页](https://docs.adobe.com/help/en/experience-manager-65/authoring/aem-adobe-campaign/target-adobe-campaign.html#setting-up-segmentation-in-aem)。

* **要成功同步，Experience Manager中的区段名称必须与Campaign中的区段名称完全匹配。**