---
title: 关于 Campaign-Experience Manager 集成
description: 通过Adobe Experience Manager集成，您可以直接在AEM中创建内容，并在以后的Adobe Campaign中使用它。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: ff94f69b-3036-4103-a841-6b85feb0eb7e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 1%

---

# 关于 Campaign-Experience Manager 集成{#integrating-with-experience-manager}

Adobe Campaign Standard与Adobe Experience Manager之间的这种集成允许您在Adobe Campaign电子邮件中使用在Adobe Experience Manager中创建的内容。

因此，您可以充分利用Adobe Experience Manager的内容编辑功能以及Adobe Campaign的交付和数据管理功能。 请注意，您无法对从Adobe Experience Manager导入的内容执行A/B测试。

Adobe Campaign Standard与Adobe Experience Manager 6.1、6.2、6.3、6.4和6.5兼容。以下部分概述了您可以执行的操作。 有关详细信息，请参阅专用于[配置](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html?lang=zh-Hans)和集成的[使用](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/campaign.html?lang=zh-Hans)的部分。

>[!NOTE]
>
> Adobe Campaign Standard模板在Adobe Experience Manager 6.5中不再可用。

## 关于如何使用Campaign-Experience Manager集成的提示 {#tips-aem}

* **了解要与集成一起使用的模板**

  由于电子邮件模板在Adobe Experience Manager中可编辑，因此在Adobe Experience Manager中编辑任何模板看上去可能会更容易。 但是，某些模板并不容易适应。 不建议对此集成使用特定于某个客户的个性化模板，这些模板应直接在Adobe Campaign Standard中编辑。

  有关模板的更多信息，请参阅此[页面](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html?lang=zh-Hans)。

* **确保在实施期间配置了外部化器**

  在实施Adobe Campaign Standard的Experience Manager时配置外部化器，可以将资源路径转换为URL。 这样，您就可以使图像在页面上可见。 如果未正确配置Externalizer，则您的电子邮件将包含损坏的图像。

  要了解如何配置外部化器，请参阅此[页面](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/externalizer.html?lang=zh-Hans)。

* **组织您的电子邮件模板以避免误用。**

  保持模板的组织可确保适当的模板位于适当的文件夹中，并且不会错误地选择错误的模板。 在实施过程中，应创建路径以将模板保存在正确的位置。

  有关模板的更多信息，请参阅此[页面](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html?lang=zh-Hans#template-availability)。

* **使用现成的组件快速入门。**

  如果模板不复杂，适用于Adobe Campaign Standard的Adobe Experience Manager中的现成组件可以帮助您快速入门。
在Experience Manager中有七个现成的组件可供您开始使用：

   * 标题
   * 图像
   * 链接
   * Scene7图像模板
   * 目标引用
   * 文本和图像
   * 文本和Personalization

* **电子邮件HTML不同于WebHTML**

  请务必了解，您不能将Web内容中使用的相同组件用于电子邮件模板。 使用现成组件可确保您的组件与电子邮件兼容。

* **从模板中取消内容链接并重复使用这些内容。**

  在Campaign Standard中设置电子邮件并选择Experience Manager模板时，您只能选择尚未链接到其他营销策划的模板。 否则，如果您在Adobe Experience Manager中更改了一个营销活动的内容并刷新，则可能会无意中影响另一个营销活动中的内容。
为了避免这种情况，一旦您完成了模板的使用，就可以取消其链接以再次使用。 您只需选择模板并单击&#x200B;**[!UICONTROL Delete the link with Adobe Experience Manager content]**&#x200B;即可。

* **使用Adobe Experience Manager创建Adobe Campaign Standard的电子邮件变体。**

  通过此集成，您可以使用分段轻松地将一封电子邮件转换为多个版本。
要了解如何在Adobe Experience Manager中设置分段以及如何创建包含目标内容的电子邮件，请参阅此[页面](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/target-adobe-campaign.html?lang=zh-Hans#setting-up-segmentation-in-aem)。

* **为了成功同步，Experience Manager中的区段名称必须与Campaign中的区段名称完全匹配。**
