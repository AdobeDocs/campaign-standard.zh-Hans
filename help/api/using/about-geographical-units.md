---
title: 关于地理单位
description: 进一步了解地理单位和API。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 5%

---


# 关于地理单位 {#about-geographical-units}

>[!CAUTION]
>
>地理单位功能在Campaign Standard18.7版本中已弃用。
>
>因此，从18.7版本开始，新Campaign Standard实例以及未创建地理单位的现有实例将无法实施此功能。
>
>有关更多信息，请参阅 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=zh-Hans#release-notes">已弃用的功能</a> 页面。

的 **geoUnitBase** 端点允许您与地理单位进行交互，例如，允许您更新其属性或更新用户档案的单位。

的 **地理单位** 扩展用户档案资源时，会将字段添加到用户档案。 因此，请记住始终使用 **profileAndServicesExt** 与地理单位交互的端点。 有关用户档案的资源扩展的更多信息，请参阅 [Campaign文档](https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles).
