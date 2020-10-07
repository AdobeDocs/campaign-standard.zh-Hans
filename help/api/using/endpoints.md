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
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 端点 {#endpoints}

Adobe CampaignREST API的可用端点：

* **/profileAndServices**:与开箱即用字段交互。 此端点无法访问扩展字段。
* **/profileAndServicesExt**:与在用户档案或服务自定义资源扩展期间添加的自定义字段交互。 For more on custom resources, refer to [this section](../../api/using/custom-resources.md).
* **/&lt;transactionalAPI>**:与事务性消息API交互(事务性消息API端点的名称取决于您的实例配置)。 如需详细信息，请参阅[此部分](../../api/using/managing-transactional-messages.md)。
* **/workflow/execution**:与工作流互动。 如需详细信息，请参阅[此部分](../../api/using/controlling-a-workflow.md)。
* **/privacy/privacyTool**:与隐私API交互，允许自动处理隐私请求。 如需详细信息，请参阅[此部分](../../api/using/creating-a-privacy-request.md)。
* **/history**:检索用户档案营销历史。 有关活动中集成客户用户档案的更多信息，请参阅 [活动文档](https://helpx.adobe.com/campaign/standard/audiences/using/integrated-customer-profile.html)。

默认情况下，profileAndServices和profileAndServicesExt **API的****可用主要资源** 为：

* **/用户档案**:与用户档案库中的活动交互。 要向服务添加用户档案，请使 **用/service** endpoint。 有关活动中用户档案的详细信息，请参阅 [活动文档](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html)。
* **/service**:管理订阅服务。 有关活动中服务的更多信息，请参阅 [活动文档](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html)。

>[!NOTE]
>
>所有已扩展或创建的其他资源仅通过 **ProfileAndServicesExt** API可用。 它们必须链接到 **用户档案** 资源，才能被访问。
