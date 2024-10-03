---
title: Campaign Standard API 快速入门
description: 通过将 Campaign 与一组技术建立联系，创建集成并构建您自己的生态系统。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: c6968252-a012-4029-bbb8-66f4f693e99b
source-git-commit: 1f4a3e06bc4882f16d87330d18f25f5ee351e11a
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 100%

---

# Campaign Standard API 快速入门 {#get-started-apis}

Campaign Standard API 旨在通过将 **Adobe Campaign Standard 与您使用的技术**&#x200B;面板连接，**使您为 Adobe Campaign Standard 创建集成，**&#x200B;并构建您自己的生态系统。

通过 Adobe Campaign Standard API，您可以访问以下功能：

<table><tr>
 <td valign="top"><a href="../../api/using/retrieving-profiles.md"><img width="50px" alt="条件" src="assets/icon_profile.svg"/></a><p><a href="../../api/using/retrieving-profiles.md">用户档案</a></p></td>
<td valign="top"><a href="../../api/using/creating-a-service.md"><img width="50px" alt="条件" src="assets/icon_services.svg"/></a><p><a href="../../api/using/creating-a-service.md">服务和订阅</a></p></td>
<td valign="top"><a href="../../api/using/interacting-with-custom-resources.md"><img width="50px" alt="条件" src="assets/icon_customresources.svg"/></a><p><a href="../../api/using/interacting-with-custom-resources.md">自定义资源</a></p></td>
<td valign="top"><a href="../../api/using/interacting-with-marketing-history.md"><img width="50px" alt="条件" src="assets/icon_marketinghistory.svg"/></a><p><a href="../../api/using/interacting-with-marketing-history.md">营销历史记录</a></p></td>
</tr>
<tr>
<td valign="top"><a href="../../api/using/creating-a-privacy-request.md"><img width="50px" alt="条件" src="assets/icon_privacy.svg"/></a><p><a href="../../api/using/creating-a-privacy-request.md">隐私管理</a></p></td>
<td valign="top"><a href="../../api/using/managing-transactional-messages.md"><img width="50px" alt="条件" src="assets/icon_transactionalmessage.svg"/></a><p><a href="../../api/using/managing-transactional-messages.md">事务型消息传递</a></p></td>
<td valign="top"><a href="../../api/using/controlling-a-workflow.md"><img width="50px" alt="条件" src="assets/icon_workflows.svg"/></a><p><a href="../../api/using/controlling-a-workflow.md">工作流</a></p></td>
<td valign="top"><a href="../../api/using/retrieving-an-organizational-unit.md"><img width="50px" alt="条件" src="assets/icon_units.svg"/></a><p><a href="../../api/using/retrieving-an-organizational-unit.md">组织单位</a></p></td>
</tr></table>

>[!NOTE]
>
>在执行 API 调用之前，请检查与您的许可协议对应的比例限制。有关详细信息，请参见[此页面](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers)。

要使用 Campaign Standard API，您需要 AdobeI/O 帐户。这是前进和发现 API 功能的必备第一步。
如需详细信息，请参阅[此部分](../../api/using/setting-up-api-access.md)。

我们提供的 API 使用 REST 接口的&#x200B;**标准概念**&#x200B;以及 JSON 负载。

>[!NOTE]
>
>所有示例都适用于 Postman，但可随意使用您最喜爱的 REST 客户端。

本文档中对所有端点进行了详尽的描述，其中包含您应当了解的关于操作 API、完整 API 引用、代码示例和快速入门指南的一般概念。

如果有任何内容缺失或错误，请咨询[社区](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)。
