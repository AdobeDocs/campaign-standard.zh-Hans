---
title: 端点
description: 进一步了解API端点。
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

* **/profileAndServices**:与开箱即用的字段交互。 扩展字段在此端点中不可访问。
* **/profileAndServicesExt**:与在“配置文件”或“服务”自定义资源扩展期间添加的自定义字段交互。 有关自定义资源的更多信息，请参阅 [此部分](../../api/using/custom-resources.md).
* **/&lt;transactionalapi>**:与事务型消息API交互（事务型消息API端点的名称取决于您的实例配置）。 如需详细信息，请参阅[此部分](../../api/using/managing-transactional-messages.md)。
* **/workflow/execution**:与工作流交互。 如需详细信息，请参阅[此部分](../../api/using/controlling-a-workflow.md)。
* **/privacy/privacyTool**:与隐私API交互，以允许自动处理隐私请求。 如需详细信息，请参阅[此部分](../../api/using/creating-a-privacy-request.md)。
* **/history**:检索用户档案的营销历史记录。 有关Campaign中整合的客户用户档案的更多信息，请参阅 [Campaign文档](https://helpx.adobe.com/campaign/standard/audiences/using/integrated-customer-profile.html).

默认情况下，可用于 **profileAndServices** 和 **profileAndServicesExt** API包括：

* **/profile**:与Campaign数据库中的用户档案交互。 要向服务添加用户档案，请使用 **/service** 端点。 有关Campaign中用户档案的更多信息，请参阅 [Campaign文档](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html).
* **/service**:管理订阅服务。 有关Campaign中服务的更多信息，请参阅 [Campaign文档](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html).

>[!NOTE]
>
>已扩展或已创建的所有其他资源均可通过 **ProfileAndServicesExt** 仅限API。 它们必须链接到 **用户档案** 资源，以便可访问。
