---
solution: Campaign Standard
product: campaign
title: 端点
description: 进一步了解API端点。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 10%

---


# 端点 {#endpoints}

Adobe CampaignREST API的可用端点：

* **/profileAndServices**:与开箱即用字段交互。此端点无法访问扩展字段。
* **/profileAndServicesExt**:与在用户档案或服务自定义资源扩展期间添加的自定义字段交互。有关自定义资源的详细信息，请参阅[本节](../../api/using/custom-resources.md)。
* **/&lt;transactionalapi>**:与事务性消息API交互(事务性消息API端点的名称取决于您的实例配置)。如需详细信息，请参阅[此部分](../../api/using/managing-transactional-messages.md)。
* **/workflow/execution**:与工作流互动。如需详细信息，请参阅[此部分](../../api/using/controlling-a-workflow.md)。
* **/privacy/privacyTool**:与隐私API交互，允许自动处理隐私请求。如需详细信息，请参阅[此部分](../../api/using/creating-a-privacy-request.md)。
* **/history**:检索用户档案营销历史。有关活动中集成客户用户档案的详细信息，请参阅[活动文档](https://helpx.adobe.com/campaign/standard/audiences/using/integrated-customer-profile.html)。

默认情况下，**profileAndServices**&#x200B;和&#x200B;**profileAndServicesExt** API的可用主要资源为：

* **/用户档案**:与用户档案库中的活动交互。要向服务添加用户档案，请使用&#x200B;**/service**&#x200B;端点。 有关活动中用户档案的详细信息，请参阅[活动文档](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html)。
* **/service**:管理订阅服务。有关活动中服务的详细信息，请参阅[活动文档](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html)。

>[!NOTE]
>
>所有已扩展或已创建的其他资源只能通过&#x200B;**ProfileAndServicesExt** API使用。 它们必须链接到&#x200B;**用户档案**&#x200B;资源，才能访问。
