---
title: 关于 Campaign-Experience Manager 集成
description: 通过Adobe Experience Manager集成，您可以直接在AEM中创建内容，稍后在Adobe Campaign中使用它。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: ff94f69b-3036-4103-a841-6b85feb0eb7e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 1%

---

# 关于 Campaign-Experience Manager 集成{#integrating-with-experience-manager}

Adobe Campaign Standard与Adobe Experience Manager之间的此集成允许您在Adobe Campaign电子邮件中使用在Adobe Experience Manager中创建的内容。

因此，您可以充分利用Adobe Experience Manager内容编辑功能以及Adobe Campaign的交付和数据管理功能。 请注意，您无法对从Adobe Experience Manager导入的内容执行A/B测试。

Adobe Campaign Standard与Adobe Experience Manager 6.1、6.2、6.3、6.4和6.5兼容。以下部分概述了可以执行的操作。 有关更多信息，请参阅[配置](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html)和[use](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/campaign.html)集成的专述章节。

>[!NOTE]
>
> Adobe Campaign Standard模板在Adobe Experience Manager 6.5中不再可用。

## 有关如何使用Campaign-Experience Manager集成的提示 {#tips-aem}

* **了解要与集成一起使用的模板**

   由于电子邮件模板在Adobe Experience Manager中可编辑，因此在Adobe Experience Manager中编辑任何模板都可能会比较容易。 但某些模板并不容易适应。 不建议为此集成编辑特定于一位客户的个性化模板，应直接在Adobe Campaign Standard中编辑。

   有关模板的更多信息，请参阅此[页面](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html)。

* **确保在实施期间配置了外部器**

   在为Adobe Campaign Standard实施Experience Manager时配置外部器，可以将资源路径转换为URL。 这样，您就可以在页面上显示图像。 如果外部器配置不正确，则电子邮件中将包含损坏的图像。

   要了解如何配置外部器，请参阅此[页面](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/externalizer.html)。

* **整理电子邮件模板以避免误用。**

   保持模板的有序性可确保适当的模板位于适当的文件夹中，并且不会因错误而选择错误的模板。 在实施过程中，应创建路径以将模板保存到正确的位置。

   有关模板的更多信息，请参阅此[页面](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html#template-availability)。

* **开箱即用组件快速入门。**

   适用于Adobe Campaign Standard的Adobe Experience Manager中的现成组件可帮助您在模板不复杂时快速入门。
Experience Manager中有七个现成的组件可供您开始使用：

   * 标题
   * 图像
   * 链接
   * Scene7图像模板
   * 目标参考
   * 文本和图像
   * 文本与个性化

* **电子邮件的HTML与Web的HTML不同**

   请务必了解，您不能将Web内容中使用的相同组件用于电子邮件模板。 使用现成的组件可确保组件在电子邮件中兼容。

* **取消内容与模板的链接，并反复重复使用它们。**

   在Campaign Standard中设置电子邮件并选择Experience Manager模板时，您只能选择一个尚未链接到其他营销活动的电子邮件。 否则，如果您在Adobe Experience Manager中为一个营销活动更改内容并进行刷新，则可能会无意中影响另一个营销活动中的内容。
要避免这种情况，在您使用完模板后，可以取消链接以再次使用该模板。 您只需选择模板并单击**[!UICONTROL Delete the link with Adobe Experience Manager content]**&#x200B;即可。

* **使用Adobe Experience Manager为Adobe Campaign Standard创建各种电子邮件。**

   通过此集成，您可以通过分段轻松地将一封电子邮件转换为多个版本。
要了解如何在Adobe Experience Manager中设置分段以及如何创建包含目标内容的电子邮件，请参阅此[page](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/target-adobe-campaign.html#setting-up-segmentation-in-aem)。

* **要成功同步，Experience Manager中的区段名称必须与Campaign中的区段名称完全匹配。**
