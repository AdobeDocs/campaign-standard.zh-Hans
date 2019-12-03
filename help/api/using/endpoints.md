---
title: 端点
description: 进一步了解API端点。
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
source-git-commit: f251e4b5187aa09f65a5d8d6215f208a09cd9159

---


# 端点 {#endpoints}

Adobe Campaign REST API的可用端点：

* **/profileAndServices**:与开箱即用的字段交互。 此端点无法访问扩展字段。
* **/profileAndServicesExt**:与在配置文件或服务自定义资源扩展期间添加的自定义字段交互。 For more on custom resources, refer to [this section](../../api/using/custom-resources.md).
* **/&lt;transactionalAPI&gt;**:与事务消息API交互（事务消息API端点的名称取决于您的实例配置）。 如需详细信息，请参阅[此部分](../../api/using/managing-transactional-messages.md)。
* **/workflow/execution**:与工作流交互。 如需详细信息，请参阅[此部分](../../api/using/controlling-a-workflow.md)。
* **/privacy/privacyTool**:与隐私API交互，允许自动处理隐私请求。 如需详细信息，请参阅[此部分](../../api/using/creating-a-privacy-request.md)。
* **/history**:检索档案的营销历史记录。 有关Campaign中集成客户档案的更多信息，请参阅 [Campaign文档](https://helpx.adobe.com/campaign/standard/audiences/using/integrated-customer-profile.html)。

默认情况下，profileAndServices和profileAndServicesExt **API的可用****** 主要资源为：

* **/profile**:与Campaign数据库中的配置文件交互。 要向服务添加配置文件，请使用 **/service端点** 。 有关Campaign中配置文件的详细信息，请参阅 [Campaign文档](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html)。
* **/service**:管理订阅服务。 有关Campaign中服务的详细信息，请参阅 [Campaign文档](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html)。

>[!NOTE]
>
>所有已扩展或创建的其他资源仅通过 **ProfileAndServicesExt** API可用。 它们必须链接到 **Profile** 资源才能访问。
