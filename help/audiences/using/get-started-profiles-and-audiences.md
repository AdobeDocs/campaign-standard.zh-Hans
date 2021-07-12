---
solution: Campaign Standard
product: campaign
title: 用户档案和受众快速入门
description: 定义目标人群、选择受众、筛选收件人、收集数据和更新档案。
audience: audiences
content-type: reference
topic-tags: about-profiles-and-audiences
feature: 用户档案
role: User
level: Beginner
exl-id: b4de2f1a-09ec-486d-b1ef-66208cbe211f
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '605'
ht-degree: 22%

---

# 用户档案和受众快速入门{#about-profiles-and-audiences}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_segment.svg" width="60px"><p><a href="#segmenting-targeting">分段和定位</a></p></td>
<td><img src="assets/do-not-localize/icon_permission.svg" width="60px"><p><a href="#permission">许可和同意</a></p></td>
<td><img src="assets/do-not-localize/icon_privacy.svg" width="60px"><p><a href="#privacy">隐私合规性</a></p></td></tr>
</table>

通过 Campaign 集成客户用户档案，可以在一个视图内跨所有渠道跟踪与客户的每次互动，从而为客户提供相关的个性化信息。

按受众细分数据库，以优化营销活动的目标。

使用服务和登陆页管理客户权限和许可，以设置简单的选择加入和选择退出机制。

## 分段和定位 {#segmenting-targeting}

<img src="assets/do-not-localize/icon_segment.svg" width="60px">

创建营销活动或消息时，您可以通过从Campaign数据库的联系人中选择、使用简单或高级标准，或选择受众，来指定投放的目标。

使用&#x200B;**集成的客户配置文件**、**自定义区段**&#x200B;和&#x200B;**控制组**&#x200B;更有效地识别所有渠道中的客户。 如果您知道客户、兴趣、人口统计和渠道偏好，就可以更轻松地创建引人注意的个性化体验。

Adobe Campaign可实时构建丰富的客户用户档案，以便您在客户偏好发生变化时提供更相关的个性化优惠。 此外，Adobe Campaign还集成了高级分析、数据管理和定位功能以构建受众。

**** 用户档案是存储在数据库中的各个联系人。每个用户档案都对应于数据库中的一个条目，其中包含要定向、鉴别和单独跟踪该用户档案的必要信息：Adobe Campaign可以跟踪来自在线和离线渠道的每次交互，并将其合并到单个用户档案中。

**** 受众是基于特定条件或一组条件构建的用户档案列表。使用工作流和查询编辑器，您可以根据您对营销活动、其活动和营销历史记录中的信息，构建受众，以便被营销活动定位。 这样，您就可以过滤订阅的用户档案、示例或根据无限数量的标准创建目标受众。

阅读更多:

* [关于用户档案](../../audiences/using/about-profiles.md)
* [使用中的用户档案](../../audiences/using/active-profiles.md)
* [管理测试用户档案](../../audiences/using/managing-test-profiles.md)
* [扩充 Campaign 数据库](../../audiences/using/enriching-campaign-database.md)
* [关于受众](../../audiences/using/about-audiences.md)
* [选择消息的受众](../../audiences/using/selecting-an-audience-in-a-message.md)
* [添加对照组](../../sending/using/control-group.md)

## 许可和同意 {#permission}

<img src="assets/do-not-localize/icon_permission.svg"  width="60px">

在开始向联系人发送邮件之前，您需要确保获得其许可。 如果没有，则您的电子邮件可能会被标记为垃圾邮件，这将影响您的平台交付能力。 要确保构建正常的配置文件数据库，请首先保护此权限。

通过Campaign，我们建议您使用&#x200B;**简单的选择加入和选择退出机制**&#x200B;通过[服务](../../audiences/using/creating-a-service.md)和[登陆页面](../../channels/using/getting-started-with-landing-pages.md)来更新您的联系信息并扩展数据库。

如果在消息中提供&#x200B;**退订链接**，则在必要时可将用户档案添加到阻止列表，从而提高平台投放能力。 有关阻止列表管理的更多信息，请参阅[关于Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)中的选择启用和选择禁用。

>[!IMPORTANT]
>
>您需要遵循[Adobe Campaign可接受的使用策略](https://www.adobe.com/legal/terms/aup.html)。

阅读更多:

* [关于订阅](../../audiences/using/about-subscriptions.md)
* [关于 Campaign 中的选择启用和选择禁用](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

## 隐私合规性 {#privacy}

<img src="assets/do-not-localize/icon_privacy.svg" width="60px">

Adobe Campaign提供了一套工具，可帮助您遵守&#x200B;**GDPR、CCPA和其他隐私法的**&#x200B;隐私合规性。

在本[中了解有关隐私管理以及我们提供的用于管理访问权、被遗忘权、同意权、数据保留权和用户角色的功能的详细信息。](https://helpx.adobe.com/cn/campaign/kb/campaign-privacy.html)

[此部分](../../start/using/privacy.md)中介绍了Campaign中的隐私和同意以及如何管理它们。 您还会找到最佳实践，以帮助您在使用我们的服务时遵守隐私规定。

## 其他资源

* [将 Adobe Experience Platform 受众引入 Campaign](../../integrating/using/ingest-aep-data.md)
* [使用Microsoft Dynamics 365](../../integrating/using/d365-acs-get-started.md)
* [Adobe共享受众](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md)
* [使用工作流导入用户档案](../../automating/using/creating-import-workflow-templates.md)
* [用户档案和受众视频](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/profiles-and-audiences/creating-profiles-and-audiences.html)
