---
title: 关于隐私管理
description: 了解关于使用API进行隐私管理的更多信息
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
source-git-commit: 210289d44f0ad0ebf0b2654f6e9795adad7dd458
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 0%

---


# 关于隐私管理 {#about-privacy-management}

Campaign StandardAPI提供了一些功能，允许自动处理与GDPR和CCPA等隐私法规相关的请求。

您可以执行的操作如下：

* 创建新的隐私请求，
* 监控隐私请求，
* 检索隐私数据文件，
* 管理配置文件的CCPA选择退出状态。

隐私API终结点为&#x200B;**/privacy/privacyTool**。 PrivacyTool资源描述和关联的过滤器在资源元数据中可用。 请参阅[元数据机制](../../api/using/metadata-mechanism.md)。

使用&#x200B;**ccpaOptOut**&#x200B;配置文件属性管理CCPA选择退出。

有关Adobe Campaign Standard和隐私合规性的更多信息，请参阅[专用文档](../../start/using/privacy-requests.md)。
