---
title: 端点
description: 了解有关API端点的更多信息。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 9f6d3da6-374d-47f5-bc8f-b31b19cbb5ca
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 10%

---

# 端点 {#endpoints}

Adobe Campaign REST API的可用端点：

* **/profileAndServices**：与开箱即用的字段交互。 不能使用此端点访问扩展字段。
* **/profileAndServicesExt**：与Profile或Services自定义资源扩展期间添加的自定义字段交互。 有关自定义资源的更多信息，请参阅 [本节](../../api/using/custom-resources.md).
* **/&lt;transactionalapi>**：与事务型消息API交互（事务型消息API端点的名称取决于您的实例配置）。 如需详细信息，请参阅[此部分](../../api/using/managing-transactional-messages.md)。
* **/workflow/execution**：与工作流交互。 如需详细信息，请参阅[此部分](../../api/using/controlling-a-workflow.md)。
* **/privacy/privacyTool**：与隐私API交互，以允许自动处理隐私请求。 如需详细信息，请参阅[此部分](../../api/using/creating-a-privacy-request.md)。
* **/history**：检索用户档案的营销历史。 有关Campaign中集成客户用户档案的更多信息，请参阅 [Campaign文档](https://helpx.adobe.com/campaign/standard/audiences/using/integrated-customer-profile.html).

默认情况下，主要资源可用于 **配置文件与服务** 和 **profileAndServiceExt** API包括：

* **/profile**：与Campaign数据库中的用户档案交互。 要将配置文件添加到服务，请使用 **/service** 端点。 有关Campaign用户档案的更多信息，请参阅 [Campaign文档](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html).
* **/service**：管理订阅服务。 有关Campaign中服务的更多信息，请参阅 [Campaign文档](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html).

>[!NOTE]
>
>已扩展或创建的所有其他资源均可通过以下网站获取： **配置文件和服务扩展** 仅限API。 它们必须链接到 **个人资料** 资源。
