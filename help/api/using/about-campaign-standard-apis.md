---
title: 关于 Campaign Standard API
description: 进一步了解Campaing Standard API。
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
source-git-commit: ea78c0d4bc338eed81a4e0cd39dfdd76837aeb2c

---


# 关于 Campaign Standard API {#about-campaign-standard-apis}

Campaign Standard API旨在让您 **为Adobe Campaign** Standard创建集成，并通过将Adobe Campaign Standard与您使用的技术面板相连， **构建您自己的生态系统** 。

通过Adobe Campaign Standard API，您可以访问以下各节中描述的各种功能：

<table>
<tr>
    <td valign="top">
        <a href="../../api/using/retrieving-profiles.md"><img alt="条件" src="assets/icon_profile.png"/></a>
        <div><a href="../../api/using/retrieving-profiles.md"><strong>配置文件</strong></a></div>
        <em>了解如何从数据库中与配置文件交互。</em>
    </td>
    <td valign="top">
        <a href="../../api/using/creating-a-service.md"><img alt="条件" src="assets/icon_services.png"/></a>
        <div><a href="../../api/using/creating-a-service.md"><strong>服务和订阅</strong></a></div>
        <em>了解如何从数据库与服务交互并管理订阅。</em>
    </td>
    <td valign="top">
        <a href="../../api/using/interacting-with-custom-resources.md"><img alt="条件" src="assets/icon_customresources.png"/></a>
        <div><a href="../../api/using/interacting-with-custom-resources.md"><strong>自定义资源</strong></a></div>
        <em>了解如何从数据库中与自定义资源交互。</em>
    </td>
    <td valign="top">
        <a href="../../api/using/interacting-with-marketing-history.md"><img alt="条件" src="assets/icon_marketinghistory.png"/></a>
        <div><a href="../../api/using/interacting-with-marketing-history.md"><strong>营销历史</strong></a></div>
        <em>了解如何与档案的营销历史互动。</em>
    </td>
</tr>
<tr>
    <td valign="top">
        <a href="../../api/using/creating-a-privacy-request.md"><img alt="条件" src="assets/icon_privacy.png"/></a>
        <div><a href="../../api/using/creating-a-privacy-request.md"><strong>隐私</strong></a></div>
        <em>了解有关隐私管理的更多信息。</em>
    </td>
    <td valign="top">
        <a href="../../api/using/managing-transactional-messages.md"><img alt="条件" src="assets/icon_transactionalmessage.png"/></a>
        <div><a href="../../api/using/managing-transactional-messages.md"><strong>交易消息</strong></a></div>
        <em>了解如何发送交易活动。</em>
    </td>
    <td valign="top">
        <a href="../../api/using/controlling-a-workflow.md"><img alt="条件" src="assets/icon_workflows.png"/></a>
        <div><a href="../../api/using/controlling-a-workflow.md"><strong>工作流</strong></a></div>
        <em>了解如何控制和触发工作流。</em>
    </td>
    <td valign="top">
        <a href="../../api/using/retrieving-an-organizational-unit.md"><img alt="条件" src="assets/icon_units.png"/></a>
        <div><a href="../../api/using/retrieving-an-organizational-unit.md"><strong>组织和地理单位</strong></a></div>
        <em>了解如何与组织和地理单位互动。</em>
    </td>
</tr>
</table>

要使用Campaign Standard API，您需要一个Adobe I/O帐户。 这是前进和发现API功能的必备第一步。
如需详细信息，请参阅[此部分](../../api/using/setting-up-api-access.md)。

我们提供的API使用 **标准概念** ，包括REST界面和JSON负载。

本文档中对所有端点进行了详尽的说明，其中包含了操作API、代码示例和快速入门指南时应了解的一般概念。 所有示例都与Postman一起使用，但您可以随意使用您喜爱的REST客户端。

>[!CAUTION]
>
>在执行API调用之前，请检查与您的许可协议相对应的比例限制。 有关详细信息，请参见[此页面](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers)。
