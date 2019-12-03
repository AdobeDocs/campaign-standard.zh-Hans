---
title: 关于地理单位
description: 进一步了解地理单位和API。
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aee0e0437cbfe578cb2f715a2433099c79dd1748

---


# 关于地理单位 {#about-geographical-units}

>[!CAUTION]
>
>Campaign Standard 18.7版本中已弃用“地理”单元功能。
因此，新的Campaign standard实例以及没有创建地理单位的现有实例无法在18.7版本开始实施此功能。
有关此功能的详细信息，请参阅“已弃 <a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html">用功能</a> ”页。

通过 **geoUnitBase端点** ，您可以与地理单元交互，例如，允许您更新其属性或更新配置文件的单元。

在扩 **展配置文件资源时** ,“地理单位”字段会添加到配置文件。 因此，请记住始终使用profileAndServicesExt **端点与** Geographical单元交互。 有关配置文件的资源扩展的详细信息，请参阅 [Campaign文档](https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles)。
