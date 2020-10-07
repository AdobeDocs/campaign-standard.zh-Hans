---
title: 关于隐私管理
description: 进一步了解使用API进行隐私管理
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 4%

---


# 关于隐私管理 {#about-privacy-management}

Campaign StandardAPI提供允许自动处理与隐私法规（如GDPR和CCPA）相关的请求的功能。

您可以执行的操作如下：

* 创建新的隐私请求，
* 监控隐私请求，
* 检索隐私数据文件，
* 管理用户档案的CCPA退出状态。

隐私API端点为 **/privacy/privacyTool**。 隐私权工具资源描述和相关过滤器在资源元数据中可用。 请参 [阅元数据机制](../../api/using/metadata-mechanism.md)。

CCPA退出是使用ccpaOptOut **用户档案属性** 管理的。

有关Adobe Campaign Standard和隐私合规性的更多信息，请参阅专 [用文档](https://helpx.adobe.com/cn/campaign/kb/acs-privacy.html)。
