---
title: 关于隐私管理
description: 进一步了解使用API进行隐私管理
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
source-git-commit: 210289d44f0ad0ebf0b2654f6e9795adad7dd458
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 0%

---


# 关于隐私管理 {#about-privacy-management}

Campaign StandardAPI提供的功能允许自动处理与隐私法规（如GDPR和CCPA）相关的请求。

您可以执行的操作如下：

* 创建新的隐私请求，
* 监控隐私请求，
* 检索隐私数据文件，
* 管理用户档案的CCPA选择退出状态。

隐私API端点为 **/privacy/privacyTool**. 资源元数据中提供了PrivacyTool资源描述和关联的过滤器。 请参阅 [元数据机制](../../api/using/metadata-mechanism.md).

CCPA选择退出使用 **ccpaOptOut** 配置文件属性。

有关Adobe Campaign Standard和隐私合规性的更多信息，请参阅 [专用文档](../../start/using/privacy-requests.md).
