---
title: Campaign和Microsoft Dynamics 365数据管理
description: 了解Campaign Standard和Microsoft Dynamics 365如何管理常见数据
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: aab6f005-f3da-4c0b-b856-da8504e611dc
source-git-commit: 17522f4df86c7fb46593472316d57b4ba4acee2b
workflow-type: tm+mt
source-wordcount: '2523'
ht-degree: 1%

---

# 最佳实践和限制 {#acs-msdyn-best-practices}

## 管理数据 {#acs-msdyn-manage-data}

对于联系人和自定义实体同步，此集成将&#x200B;**Microsoft Dynamics 365视为真实来源**。  对同步属性的任何更改应在Dynamics 365中完成，而不是在Adobe Campaign Standard中完成)。  如果在Campaign中进行了更改，则同步期间最终可能会在Campaign中覆盖这些更改，因为同步是单向的。

可以选择将该集成配置为在Dynamics 365中删除联系人时向Campaign发出配置文件删除调用，以帮助维护数据完整性。 但是，配置文件删除与隐私删除不同。 Campaign中的隐私删除将删除Campaign配置文件记录及关联的日志条目；而常规配置文件删除将仅删除Campaign配置文件记录，从而在Campaign日志中留下剩余项。 如果集成中启用了配置文件删除功能，则需要执行其他步骤才能正确处理数据主体隐私请求。 请参阅以下[隐私部分中的步骤](#manage-privacy-requests)。

## 隐私{#acs-msdyn-manage-privacy}

此集成旨在在Microsoft Dynamics 365和Adobe Campaign Standard之间传输最终用户数据。 此数据包括您的最终用户数据中包含的个人信息。  作为数据控制者，贵公司有责任遵守适用于您收集和使用个人数据的任何隐私法律法规。

此集成旨在在Microsoft Dynamics 365和Adobe Campaign Standard之间传输最终用户数据（包括但不限于个人信息，如果最终用户数据中包含此信息）。 作为数据控制者，贵公司有责任遵守适用于您收集和使用个人数据的任何隐私法律法规。

该集成不发布任何数据主体隐私（例如GDPR），也不处理任何其他隐私请求（选择退出除外）。 处理隐私请求时，您应在Microsoft Dynamics 365和Campaign(通过Adobe Experience Platform Privacy Service)中独立执行此操作。

如果您已配置集成，以便在Dynamics 365中删除联系人时向Campaign发出常规配置文件删除调用，则应执行以下步骤。 请确保在此过程中未对相关记录进行更新。

1. 向[Adobe Experience Platform Privacy Service](https://developer.adobe.com/experience-platform-apis/references/privacy-service)发送问题隐私删除请求

1. 监控请求，直到成功完成为止

1. 验证记录是否不再位于您的Campaign实例中

1. （不久之后）在Dynamics 365中发生隐私删除问题

1. 验证是否已从两个系统中删除记录


>[!IMPORTANT]
>
>如果任何Campaign自定义资源记录包含适用于客户使用Campaign的个人信息，则此类记录应链接到相应的Campaign配置文件记录（直接或通过其他自定义资源），以便配置文件记录中与隐私相关的删除也可以删除包含个人信息的链接自定义资源记录；实体之间的链接和删除选项必须配置为启用这种级联删除链接记录的功能。 个人信息不应输入到未链接到用户档案的自定义资源中。

## 选择禁用 {#opt-out}

由于Microsoft Dynamics 365和Campaign之间在选择退出属性方面的差异，以及每个客户在业务要求方面的差异，我们留出了选择退出映射作为供客户完成的练习。  务必确保选择退出在系统之间正确映射，以便最终用户保持选择退出偏好设置，并且他们不会通过已选择退出的渠道接收通信。

请注意，在选择退出映射中只能使用以下项：

* 前缀为“不再联系”的Campaign属性（例如，不再通过电子邮件联系），或

* CCPA的特定属性

有关配置文件实体字段的更多信息，可在[此处](../../developing/using/datamodel-profile.md)找到。

在Dynamics 365中，大多数选择退出字段都有“donot”前缀。但是，如果数据类型兼容，您还可以利用其他属性来实现选择退出目的。

在配置集成时，您将有机会指定企业所需的选择退出配置：

* **单向(Microsoft Dynamics 365到Campaign)**： Dynamics 365是选择退出的真实来源。 选择退出属性将从Dynamics 365同步到Campaign Standard的一个方向
* **单向(从Campaign到Microsoft Dynamics 365)**：Campaign Standard是选择退出的真实来源。 选择退出属性将在从Campaign Standard到Dynamics 365的一个方向上同步
* **双向**： Dynamics 365和Campaign Standard都是真实来源。 选择退出属性将在Campaign Standard和Dynamics 365之间双向同步

或者，如果您有单独的流程来管理系统之间的选择退出同步，则可以禁用该集成的选择退出数据流。

双向选择退出配置使用逻辑来确定要写入两个系统的值。 该逻辑将比较两个系统之间的时间戳（Dynamics 365中的记录级别更改，Campaign中的属性级别更改）以确定哪个系统占优势。 如果Campaign包含更新的时间戳，则Campaign值优先。 如果Dynamics 365包含更新的时间戳或时间戳相等，则opt-out=TRUE将获胜（假设其中一个值为TRUE）。

在[本节](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf)中了解如何选择选择加入/退出选项。

>[!NOTE]
>
>请检查Adobe Campaign中的默认分类和特定分类规则，并在适当时进行更新，然后再在此处进行更改，以确保此类更改正确应用于所有传出通信。 例如，请确保任何选择退出偏好设置的映射准确地反映收件人的意图/通信选择，并且不会无意中中断关系或事务性消息（如客户订单确认）的交付。

如果您选择了&#x200B;**双向**&#x200B;或&#x200B;**单向(Campaign to Microsoft Dynamics 365)**&#x200B;选择退出配置，Campaign选择退出数据将通过工作流定期导出到Campaign SFTP存储区域（请参阅下面的“Campaign SFTP使用情况”）。 如果Campaign选择退出工作流停止运行，您需要尽快手动重新启动，以减少错过选择退出同步的可能性。

>[!IMPORTANT]
>
>如果您需要&#x200B;**双向**&#x200B;或&#x200B;**单向(Campaign to Microsoft Dynamics 365)**&#x200B;选择退出配置，则需要向Adobe技术联系人发出请求，才能在Campaign实例上设置选择退出工作流

## Campaign SFTP使用情况

在以下用例中，您的Campaign SFTP存储将需要由集成使用。  您需要确保SFTP帐户具有足够的存储容量以适应这些用例。 超过许可的SFTP存储容量可能会严重损害Campaign、集成和/或SFTP帐户的功能使用。

| 用例 | 说明 |
|---|---|
| 双向和单向(Campaign到Microsoft Dynamics 365) | 双向和单向(Campaign到Microsoft Dynamics 365)选择退出数据流将利用Campaign SFTP存储。 Campaign工作流会将增量更改导出到SFTP文件夹。 集成将从此处获取记录并进行处理。 |
| 选择退出日志 | 在对集成进行故障诊断时，连接器的输出日志将会很有用。 可以打开/关闭输出日志。 |


>[!IMPORTANT]
>
>您对从SFTP文件夹访问和下载的信息负责。 如果信息包含个人数据，则您有责任遵守任何适用的隐私法律和法规。 [了解详情](#acs-msdyn-manage-privacy)。

## 数据管理

### 现有Campaign数据

此集成会将联系人和自定义实体从Microsoft Dynamics 365同步到Campaign。 在集成之外创建的Campaign记录（即不是由同步作业创建的）不会被集成修改，包括集成配置时存在的Campaign记录。

由于此集成使用Campaign中的&#x200B;**[!UICONTROL externalId]**&#x200B;字段将Campaign配置文件记录与Dynamics 365联系人记录同步，因此对于要从Microsoft Dynamics 365同步的记录，必须使用Microsoft Dynamics 365 **[!UICONTROL contactId]**&#x200B;填充此Campaign字段(**[!UICONTROL externalId]**)。  自定义实体也将使用Microsoft Dynamics 365唯一ID进行同步。 Campaign自定义实体将需要包含此ID属性作为表列。 externalId列可用于存储此属性值，但Campaign自定义实体不需要它。

请记住，Microsoft Dynamics 365仍然是真实来源，并且当集成在Dynamics 365端上检测更新时，可以覆盖Campaign配置文件数据。  启用集成可能还需要执行其他步骤，具体取决于您现有的部署；因此，建议您与Adobe技术联系人密切合作。

>[!NOTE]
>
>由于现有客户部署的复杂性，建议您在规划和设置集成时与Adobe技术联系人合作。

### 数据同步频率

该集成利用的架构可检测更新，并将其添加到Microsoft Dynamics 365中发生更新后不久（即，流式处理，而不是批量处理）的处理“队列”中。 因此，无需指定数据流运行频率或计划。

唯一的例外是双向和Campaign到Dynamics 365的选择退出数据流。 对于这些选择退出配置，更新的Campaign记录每天通过Campaign工作流导出到SFTP一次，之后集成工具读取文件并处理记录。

### 数据使用协议

如果您位于EMEA或APAC地区，作为此集成的一部分，您的某些数据将在美国进行处理。 有关更多信息，请参见[此章节](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

## 护栏和限制

>[!IMPORTANT]
>
>您的某些操作（例如，初始摄取记录、重放记录数据等） 可能会导致大量记录从Microsoft Dynamics 365引入到Adobe Campaign实例中。 为了降低出现性能问题的风险，建议您停止所有营销活动流程（例如，无营销活动、未运行工作流等） 直到将大量记录引入Campaign之后。

### 自定义实体

[Microsoft Dynamics 365-Adobe Campaign Standard集成](../../integrating/using/d365-acs-get-started.md)支持自定义实体，从而能够将Dynamics 365中的自定义实体同步到Campaign中的相应自定义资源。

该集成支持链接表和非链接表。

配置自定义实体数据流时，请务必注意以下事项：

* 创建和修改Campaign自定义资源是敏感操作，只能由专家用户执行。
* 对于自定义实体数据流，必须在Dynamics 365中为同步的自定义实体启用更改跟踪。
* 如果在Dynamics 365中几乎同时创建父记录和链接的子记录，则由于并行处理集成，将新子记录写入其父记录之前的Campaign的几率很小。

* 如果使用&#x200B;**1基数简单链接**&#x200B;选项在Campaign端链接了父记录和子记录，则在父记录到达Campaign之前，子记录将保持隐藏状态并且无法访问（通过UI或API）。

* （假定Campaign中有&#x200B;**1个基数简单链接**）如果在Dynamics 365中更新或删除了子记录，并且更改在父记录出现在Campaign中之前写入Campaign（不太可能，但极有可能出现），则不会在Campaign中处理该更新或删除，并会引发错误。 如果更新，则需要在Dynamics 365中再次更新相关记录才能同步更新的记录。 在删除的情况下，相关记录将需要在Campaign端单独进行处理，因为Dynamics 365中不再有要删除或更新的记录。

* 如果您遇到您认为已隐藏子记录且无法访问这些记录的情况，则可以临时将基数链接类型更改为&#x200B;**0或1个基数简单链接**&#x200B;以访问这些记录。

有关Campaign自定义资源的更全面概述可在此部分[中找到](../../developing/using/key-steps-to-add-a-resource.md)。

### 集成护栏

在计划使用此集成时，应考虑以下防护。 如果您认为超过这些护栏，请咨询您的Adobe技术代表。

* 您需要许可正确的Campaign包，以支持集成生成的引擎调用量。 超出许可引擎调用量可能会导致Campaign性能下降。

  使用以下内容帮助估算集成中的引擎调用量：

   * 记录插入（即新记录）：1个引擎调用
   * 记录删除： 1个引擎调用
   * 记录更新：2个引擎调用（如果目标记录与源记录相同，即如果促销活动记录没有更改，则仅调用1个）

  在估计整个Campaign引擎调用量时，务必要考虑其他引擎调用源，包括登陆页面、WebApps、JSSP、API、移动应用程序注册等。

  在此处查看Adobe Campaign Standard包信息：[https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html](https://helpx.adobe.com/cn/legal/product-descriptions/campaign-standard.html)

* 该集成最多支持在Campaign中首次同步到资源的总共1500万条记录。 增量同步受Adobe Campaign Standard包限制。

* 标准集成产品包括最多支持20个自定义实体，每个实体的大小最多为50列。

* 在实施集成之前，您需要创建和发布自定义资源。

* 链接表时的最大表深度为两个（即table1->table2->table3）

* 该集成为每个自定义资源最多支持5个链接的列。 在自定义资源之间链接多个列可能会对性能产生显着影响。 **0或1基数简单链接**&#x200B;优先于&#x200B;**1基数简单链接**。

* 该集成支持在原始Microsoft Dynamics 365数据类型(Boolean、Integer、Decimal、Double、String、DateTime、Date)和Adobe Campaign Standard数据类型(integer、boolean、float、double、date、datetime、string)之间进行转换。 更高级的数据类型将解释为字符串，并照原样同步。

* 可能需要在Adobe和客户之间建立载入维护窗口。

* 请注意，集成使用率显着增加或“激增”（例如，新记录或更新记录急剧增加）可能会导致数据同步速度减慢。

* 作为集成的一部分，您需要在Microsoft Azure和Dynamics 365中完成集成前配置步骤。 请参阅此页面上的配置步骤[&#128279;](../../integrating/using/d365-acs-configure-d365.md)

* 预计您会将Dynamics 365和Campaign数据模型引入集成并对其进行维护。

### 集成边界

该集成旨在解决Microsoft Dynamics 365和Campaign之间常见数据移动的一般用例，但并非旨在解决每个客户特有的每个用例：

* 该集成不会发布任何隐私删除（例如GDPR）。 客户有责任履行最终用户隐私请求；此类请求应在Campaign(通过Adobe Experience Platform Privacy Service)和Dynamics 365中单独提出。 如果需要，集成可以发布定期删除以帮助实现数据同步。   有关详细信息，请参阅[隐私部分](#manage-privacy-requests)。

* 任何配置文件或自定义实体数据都不会从Campaign同步到Dynamics 365，但选择退出信息（如果由客户配置）除外。

* Campaign订阅管理（即订阅/取消订阅）不受本机支持。

* 不支持在Dynamics 365中组合和触发Campaign电子邮件营销活动。

* 该集成&#x200B;**不支持**&#x200B;在Dynamics 365和Campaign Standard数据模型之间重新建模数据。 预期集成会将一个Dynamics 365表同步到一个Campaign表。
