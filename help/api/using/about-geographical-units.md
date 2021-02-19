---
solution: Campaign Standard
product: campaign
title: 关于地理单位
description: 进一步了解地理单位和API。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: ad7322905c69f9575e11efc9d8f68cf909dc425f
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 5%

---


# 关于地理单位{#about-geographical-units}

>[!CAUTION]
>
>Campaign Standard 18.7版本中已弃用地理单元功能。
>
>因此，新的Campaign Standard实例以及没有创建地理单位的现有实例无法在18.7版本开始实现此功能。
>
>有关详细信息，请参阅<a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=zh-Hans#release-notes">已弃用功能</a>页。

通过&#x200B;**geoUnitBase**&#x200B;端点，您可以与地理单元交互，例如，使您能够更新其属性或更新用户档案的单元。

在扩展用户档案资源时，将&#x200B;**地理单元**&#x200B;字段添加到用户档案。 因此，请记住始终使用&#x200B;**profileAndServicesExt**&#x200B;端点与地理单元交互。 有关用户档案资源扩展的详细信息，请参阅[活动文档](https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles)。
