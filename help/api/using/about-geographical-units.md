---
title: 关于地理单位
description: 了解有关地理单位和API的更多信息。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 0%

---


# 关于地理单位 {#about-geographical-units}

>[!CAUTION]
>
>地理单位功能已在Campaign Standard18.7版本中弃用。
>
>因此，从18.7版本开始，新Campaign Standard实例以及未创建地理单位的现有实例无法实现此功能。
>
>有关更多信息，请参阅<a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=zh-Hans#release-notes">已弃用的功能</a>页面。

**geoUnitBase**&#x200B;端点允许您与地理单位交互，例如，允许您更新其属性或更新用户档案的单位。

扩展配置文件资源时，**地理单位**&#x200B;字段已添加到配置文件。 因此，请记住始终使用&#x200B;**profileAndServicesExt**&#x200B;端点与地理单位交互。 有关用户档案资源扩展的更多信息，请参阅[Campaign文档](https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles)。
