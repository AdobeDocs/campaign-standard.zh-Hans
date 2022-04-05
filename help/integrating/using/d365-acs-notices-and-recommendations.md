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
source-git-commit: 4b0c4fb13cc11c06e2487e531ca96574e49b6beb
workflow-type: tm+mt
source-wordcount: '2507'
ht-degree: 1%

---

# 最佳实践和限制 {#acs-msdyn-best-practices}

## 管理数据 {#acs-msdyn-manage-data}

对于联系人和自定义实体同步，此集成将考虑 **Microsoft·动力365**.  对同步属性所做的任何更改都应在Dynamics 365中完成，而不应在Adobe Campaign Standard中完成)。  如果在Campaign中进行更改，则在同步期间，这些更改最终可能会在Campaign中被覆盖，因为同步是单向的。

可以选择将该集成配置为在Dynamics 365中删除联系人时向Campaign发出用户档案删除调用，以帮助维护数据完整性。 但是，配置文件删除与隐私删除不同。 Campaign中的隐私删除将删除Campaign用户档案记录和关联的日志条目；然而，定期用户档案删除将只删除Campaign用户档案记录，并保留Campaign日志中的残余内容。 如果集成中启用了配置文件删除功能，则需要执行其他步骤才能正确处理数据主体隐私请求。 请参阅 [下面的隐私部分](#manage-privacy-requests).

## 隐私{#acs-msdyn-manage-privacy}

此集成旨在在Microsoft Dynamics 365和Adobe Campaign Standard之间传输最终用户数据。 如果此数据包含在最终用户数据中，则该数据包含个人信息。  作为数据控制者，贵公司有责任遵守适用于您收集和使用个人数据的任何隐私法律和法规。

此集成旨在在Microsoft Dynamics 365和Adobe Campaign Standard之间传输最终用户数据(包括但不限于个人信息（如果它包含在最终用户数据中）。 作为数据控制者，贵公司有责任遵守适用于您收集和使用个人数据的任何隐私法律和法规。

该集成不会发布任何数据主体隐私（例如GDPR）删除或处理任何其他隐私请求（选择退出除外）。 处理隐私请求时，您应该在Microsoft Dynamics 365和Campaign(通过Adobe Experience Platform Privacy Service)中单独执行此操作。

如果您已将集成配置为在Dynamics 365中删除联系人时向Campaign发出定期用户档案删除调用，则应执行以下步骤。 确保在此过程中未对相关记录进行任何更新。

1. 向发出隐私删除请求 [Adobe Experience Platform Privacy Service](https://developer.adobe.com/experience-platform-apis/references/privacy-service)

1. 监视请求，直到成功完成

1. 验证记录是否不再位于Campaign实例中

1. （不久之后）在Dynamics 365中发布隐私删除

1. 验证记录是否已从两个系统中删除

以下是帮助指导您在每个系统中实施访问和/或删除隐私相关请求的链接：

* [Microsoft Dynamics 365](https://docs.microsoft.com/en-us/dynamics365/get-started/gdpr/)

* [Adobe Campaign Standard](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html)

>[!IMPORTANT]
>
>如果任何Campaign自定义资源记录包含适用于客户使用Campaign的个人信息，则此类记录应直接或通过其他自定义资源链接到相应的Campaign用户档案记录，以便与隐私相关的删除该用户档案记录也可以删除包含个人信息的链接的自定义资源记录；必须配置实体之间的链接和删除选项，以启用链接记录的这种类似级联的删除。 不应将个人信息输入到未链接到用户档案的自定义资源中。

## 选择退出 {#opt-out}

由于Microsoft Dynamics 365与Campaign之间的选择退出属性存在差异，并且每个客户的业务要求存在差异，因此选择退出映射已留作一项练习，供客户完成。  请务必确保在系统之间正确映射选择退出，以便维护最终用户的选择退出首选项，并且他们不会通过已选择退出的渠道接收通信。

请注意，只有以下内容才能在选择退出映射中使用：

* 具有前缀“不再通过联系”的营销活动属性（例如，不再通过电子邮件联系），或者

* CCPA的特定属性

有关用户档案实体字段的更多信息，请参阅 [此处](../../developing/using/datamodel-profile.md).

在Dynamics 365中，大多数选择退出字段都带有“donot”前缀，但是，如果数据类型兼容，您还可以将其他属性用于选择退出目的。

在配置集成时，您将有机会指定业务所需的选择退出配置：

* **单向(Microsoft Dynamics 365到Campaign)**:Dynamics 365是选择退出的真相来源。 选择退出属性将在从Dynamics 365到Campaign Standard的一个方向上同步
* **单向(营销活动到Microsoft Dynamics 365)**:Campaign Standard是选择退出的真相来源。 选择退出属性将在从Campaign Standard到Dynamics 365的一个方向上进行同步
* **双向**:Dynamics 365 ANDCampaign Standard都是真理的来源。 选择退出属性将在Campaign Standard和Dynamics 365之间双向同步

或者，如果您有一个单独的流程来管理系统之间的选择退出同步，则可以禁用集成的选择退出数据流。

双向选择退出配置使用逻辑确定要写入两个系统的值。 该逻辑可比较两个系统之间的时间戳（Dynamics 365中的记录级别更改，Campaign中的属性级别更改）以确定哪个系统占上风。 如果促销活动包含更新的时间戳，则促销活动值优先。 如果Dynamics 365包含更新的时间戳，或者如果时间戳相等，则选择退出=TRUE将获胜（假设其中一个值为TRUE）。

了解如何在 [此部分](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).

>[!NOTE]
>
>请在此处进行更改之前，查看并更新Adobe Campaign中的默认和特定分类规则（如果适用），以确保将此类更改正确应用于所有传出通信。 例如，请确保指向选择退出首选项的任何映射都准确反映了收件人的意图/通信选项，并且不会无意中中断关系或事务型消息（如客户订单确认）的交付。

如果您选择了 **双向** 或 **单向(营销活动到Microsoft Dynamics 365)** 选择退出配置中，Campaign选择退出数据将通过工作流定期导出到您的Campaign SFTP存储区域（请参阅下面的“Campaign SFTP使用情况”）。 如果您的Campaign选择退出工作流停止运行，您需要尽快手动重新启动，以减少错过选择退出同步的可能性。

>[!IMPORTANT]
>
>如果您需要 **双向** 或 **单向(营销活动到Microsoft Dynamics 365)** 选择退出配置中，您需要向Adobe技术联系人请求在Campaign实例中设置选择退出工作流

## 促销活动SFTP使用情况

在以下用例中，集成需要使用您的Campaign SFTP存储。  您需要确保SFTP帐户具有足够的存储容量来适应这些用例。 超过获得许可的SFTP存储容量可能会严重损害Campaign、集成和/或SFTP帐户的功能使用。

| 用例 | 说明 |
|---|---|
| 双向和单向(促销活动到Microsoft Dynamics 365) | 双向和单向(从Campaign到Microsoft Dynamics 365)选择退出数据流将利用Campaign SFTP存储。 营销活动工作流会将增量更改导出到SFTP文件夹。 从那里，集成将提取记录和流程。 |
| 选择退出日志 | 对集成进行故障诊断时，连接器的输出日志将很有用。 可以打开/关闭输出日志。 |


>[!IMPORTANT]
>
>您负责从SFTP文件夹访问和下载的信息。 如果信息包含个人数据，您有责任遵守任何适用的隐私法律和法规。 [了解详情](#acs-msdyn-manage-privacy)。

## 数据管理

### 现有Campaign数据

此集成会将Microsoft Dynamics 365中的联系人和自定义实体同步到Campaign。 集成不会修改在集成之外创建的Campaign记录（即不是由同步作业创建的），包括集成配置时存在的Campaign记录。

由于此集成使用 **[!UICONTROL externalId]** 字段，以将Campaign用户档案记录与Dynamics 365联系人记录同步，此Campaign字段(**[!UICONTROL externalId]** )必须使用Microsoft Dynamics 365填充 **[!UICONTROL contactId]** ，以获取您希望从Microsoft Dynamics 365同步的记录。  自定义实体也使用Microsoft Dynamics 365唯一ID进行同步。 Campaign自定义实体需要将此ID属性作为表列包含在内。 externalId列可用于存储此属性值，但Campaign自定义实体不需要它。

请记住，Microsoft Dynamics 365仍然是真相的来源，并且由于集成检测到Dynamics 365端的更新，因此可以覆盖Campaign配置文件数据。  根据您的现有部署，可能需要执行其他步骤来启用集成；因此，建议您与Adobe技术联系人密切合作。

>[!NOTE]
>
>由于现有Adobe部署的复杂性，建议您在规划和设置集成时与客户技术联系人联系。

### 数据同步频率

该集成利用一种架构，该架构允许在Microsoft Dynamics 365中发生更新后不久（即，流处理，而不是批处理），便检测更新并将其添加到处理“队列”中。 因此，无需指定数据流运行频率或计划。

Dynamics 365选择退出数据流的双向和Campaign是例外。 对于这些选择退出配置，更新的Campaign记录将每天通过Campaign工作流导出到SFTP，然后集成工具读取文件并处理记录。

### 数据使用协议

如果您位于EMEA或APAC地区，则部分数据将在美国作为此集成的一部分进行处理。 有关更多信息，请参见[此章节](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

## 护栏和限制

>[!IMPORTANT]
>
>您的某些操作（例如，初始摄取记录、重播记录数据等） 可能会导致大量记录从Microsoft Dynamics 365摄取到Adobe Campaign实例。 为降低出现性能问题的风险，建议您停止所有Campaign流程（例如，没有营销活动、没有运行工作流等） 直到将大量记录摄取到Campaign中。

### 自定义实体

的 [Microsoft Dynamics 365-Adobe Campaign Standard集成](../../integrating/using/d365-acs-get-started.md) 支持自定义实体，使Dynamics 365中的自定义实体能够同步到Campaign中的相应自定义资源。

该集成支持链接的表和未链接的表。

配置自定义实体数据流时，请务必注意以下事项：

* 创建和修改Campaign自定义资源是敏感操作，必须仅由专家用户执行。
* 对于自定义实体数据流，必须在Dynamics 365中为同步的自定义实体启用更改跟踪。
* 如果由于集成的并行处理，在Dynamics 365中几乎同时创建了父记录和链接的子记录，则在其父记录之前，可能会略有可能将新子记录写入Campaign。

* 如果父项和子项在营销活动端使用 **1个基数简单链接** 选项，则在父记录到达Campaign之前，子记录将保持隐藏状态且不可访问（通过UI或API）。

* (假定 **1个基数简单链接** （在Campaign中）如果子记录在Dynamics 365中更新或删除，并且该更改在父记录在Campaign中显示之前写入Campaign（不可能，但是是远程可能），则该更新或删除不会在Campaign中处理，并且会引发错误。 在更新时，需要在Dynamics 365中再次更新相关记录，以同步更新的记录。 在删除的情况下，需要在Campaign端单独处理相关记录，因为Dynamics 365中不再有要删除或更新的记录。

* 如果您遇到这样一种情况，即您认为自己有隐藏的子记录并且无法访问这些记录，则可以临时将基数链接类型更改为 **0或1个基数简单链接** 来访问这些记录。

可以找到Campaign自定义资源的更全面概述 [在此部分中](../../developing/using/key-steps-to-add-a-resource.md).

### 集成护栏

在计划使用此集成时，应考虑以下护栏。 如果您认为超出这些防护，请咨询您的Adobe技术代表。

* 您需要授权适当的Campaign包，以支持由集成生成的引擎调用量。 超过授权的引擎调用量可能会导致Campaign性能下降。

   使用以下代码帮助估算集成中的引擎调用量：

   * 记录插入（即，新记录）：1个引擎呼叫
   * 记录删除：1个引擎呼叫
   * 记录更新：2个引擎调用（如果目标记录与源记录相同，即，如果促销活动记录没有更改，则仅调用1个调用）

   在估算整个Campaign引擎调用量时，务必要考虑其他引擎调用源，包括登陆页面、WebApps、JSSP、API、移动设备应用程序注册等。

   可在此处查看Adobe Campaign Standard包信息： [https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html)

* 该集成最多支持1,500万条记录，用于与Campaign中的资源进行初始同步。 增量同步受Adobe Campaign Standard包的限制。

* 标准集成产品包括对最多20个自定义实体的支持，每个实体的大小最多为50列。

* 在实施集成之前，您需要创建并发布自定义资源。

* 链接表时最大表深度为2（即table1->table2->table3）

* 该集成支持每个自定义资源最多5个链接列。 在自定义资源之间链接多个列可能会对性能产生显着影响。 **0或1个基数简单链接** 优先于 **1个基数简单链接**.

* 该集成支持基元Microsoft Dynamics 365数据类型（布尔、整数、小数、双精度、字符串、DateTime、日期）和Adobe Campaign Standard数据类型（整数、布尔、浮点、双精度、日期、日期时间、字符串）之间的转换。 更高级的数据类型将解释为字符串并按原样同步。

* 可能需要在Adobe和客户之间建立入门维护窗口。

* 请注意，集成的使用量显着增加或“激增”（例如，新记录或更新记录的急剧增加）可能会导致数据同步速度减慢。

* 在集成中，您将需要完成Microsoft Azure和Dynamics 365中的集成前配置步骤。 请参阅配置步骤 [本页](../../integrating/using/d365-acs-configure-d365.md)

* 预计您会将Dynamics 365和Campaign数据模型引入集成并进行维护。

### 集成边界

该集成旨在解决Microsoft Dynamics 365与Campaign之间常见数据移动的一般用例，但它并非旨在解决每个客户特定的每个用例：

* 该集成不会发出任何隐私（例如GDPR）删除。 履行最终用户隐私请求的责任由客户承担；此类请求应在Campaign(通过Adobe Experience Platform Privacy Service)和Dynamics 365中独立进行。 如果需要，集成可发出常规删除以帮助进行数据同步。   审阅 [隐私部分](#manage-privacy-requests) 以了解更多信息。

* 除选择退出信息（如果客户进行配置）外，任何用户档案或自定义实体数据都不会从Campaign同步到Dynamics 365。

* 本地不支持促销活动订阅管理（即订阅/取消订阅）。

* 不支持在Dynamics 365中编写和触发Campaign电子邮件促销活动。

* 该集成可执行 **not** 支持在Dynamics 365和Campaign Standard数据模型之间重构数据。 预计该集成会将一个Dynamics 365表同步到一个Campaign表。
