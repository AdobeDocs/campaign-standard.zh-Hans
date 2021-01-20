---
solution: Campaign Standard
product: campaign
title: 活动和Microsoft Dynamics 365数据管理
description: 了解Campaign Standard和Microsoft Dynamics 365如何管理常见数据
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: cce30fd5cd3d5d63563d1dab3bb1e7554c26fb3e
workflow-type: tm+mt
source-wordcount: '2467'
ht-degree: 1%

---


# 最佳实践和限制 {#acs-msdyn-best-practices}

## 管理数据{#acs-msdyn-manage-data}

对于联系人和自定义实体同步，此集成将&#x200B;**Microsoft Dynamics 365视为真**&#x200B;的源。  对同步属性所做的任何更改应在Dynamics 365中进行，而不应在Adobe Campaign Standard进行)。  如果更改是在活动中进行的，则在同步过程中最终可能会在活动中覆盖这些更改，因为同步是单向的。

该集成可以选择性地配置为在Dynamics 365中删除联系人时向活动发出用户档案删除调用，以帮助保持数据完整性。 但是，用户档案删除与隐私删除不同。 活动中的隐私删除将删除活动用户档案记录和相关日志条目；但是，定期用户档案删除只会删除活动用户档案记录，而保留活动日志中的残余物。 如果在集成中启用用户档案删除功能，则需要执行其他步骤才能正确处理数据主体隐私请求。 请参阅下面](#manage-privacy-requests)的[隐私部分中的步骤。

## 隐私{#acs-msdyn-manage-privacy}

此集成旨在在Microsoft Dynamics 365和Adobe Campaign Standard之间传输最终用户数据。 如果个人信息包含在最终用户数据中，则此数据包括个人信息。  作为公司管理者，您有责任遵守适用于您收集和使用个人数据的任何隐私法律和法规。

此集成旨在在Microsoft Dynamics 365和Adobe Campaign Standard之间传输最终用户数据（包括但不限于个人信息，如果其包含在最终用户数据中）。 作为公司管理者，您有责任遵守适用于您收集和使用个人数据的任何隐私法律和法规。

该集成不会发布任何数据主体隐私（例如，GDPR）删除或处理任何其他隐私请求（退出除外）。 处理隐私请求时，您应分别在Microsoft Dynamics 365和活动(通过Adobe Experience Platform Privacy Service)中执行。

如果已将集成配置为在Dynamics 365中删除联系人时向活动发出定期用户档案删除调用，则应遵循以下步骤。 确保在此过程中未对相关记录进行任何更新。

1. 向[Adobe Experience Platform Privacy Service](https://www.adobe.io/apis/experiencecloud/gdpr.html)发出隐私删除请求

1. 监视请求，直到它成功完成

1. 验证记录不再在活动实例中

1. （不久之后）在Dynamics 365中删除问题隐私

1. 验证记录是否已从两个系统中删除

下面是帮助指导您在每个系统中实施访问和／或删除隐私相关请求的链接：

* [Microsoft Dynamics 365](https://docs.microsoft.com/en-us/dynamics365/get-started/gdpr/)

* [Adobe Campaign Standard](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html)

>[!IMPORTANT]
>
>如果任何活动自定义资源记录包含适用于客户使用活动的个人信息，则此类记录应链接到相应的活动用户档案记录（直接或通过其他自定义资源），以便与用户档案记录相关的隐私删除也可以删除包含个人信息的链接自定义资源记录；必须配置实体之间的链接和删除选项，以启用链接记录的类层叠删除。 个人信息不应输入到未链接到用户档案的自定义资源中。

## 退出{#opt-out}

由于Microsoft Dynamics 365和活动之间的选择退出属性存在差异，以及每个客户的业务要求存在差异，因此选择退出映射已被留作客户完成的一项练习。  务必确保在系统之间正确映射退出功能，以便最终用户选择退出首选项得以保持，并且他们不会通过已选择退出的渠道接收通信。

请注意，只有以下选项才能用于退出映射：

* 活动属性带有“不再通过电子邮件联系”前缀（例如，不再通过电子邮件联系），或

* CCPA的特定属性

有关用户档案实体字段的详细信息，请在[此处](../../developing/using/datamodel-profile.md)找到。

在Dynamics 365中，大多数选择退出字段都有“donot”前缀，但是，如果数据类型兼容，您也可以将其他属性用于选择退出目的。

设置集成时，您将有机会指定您的企业需要的退出配置：

* **单向(Microsoft Dynamics 365到活动)**:Dynamics 365是退出的真相。退出属性将沿一个方向从Dynamics 365同步到Campaign Standard
* **单向(活动到Microsoft Dynamics 365)**:Campaign Standard是选择退出的真相来源。退出属性将沿一个方向从Campaign Standard同步到Dynamics 365
* **双向**:Dynamics 365和Campaign Standard都是真理的源泉。退出属性将在Campaign Standard和Dynamics 365之间双向同步

或者，如果您有单独的过程来管理系统之间的退出同步，则可禁用集成的退出数据流。

双向选择退出配置使用逻辑确定要写入两个系统的值。 该逻辑比较两个系统之间的时间戳(Dynamics 365中的记录级别更改，活动中的属性级别更改)以确定哪个系统占上风。 如果活动包含更新的时间戳，则活动值优先。 如果Dynamics 365包含更新的时间戳，或者如果时间戳相等，则opt-out=TRUE将获胜（假定其中一个值为TRUE）。

了解如何在[本节](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf)中选择加入／退出选项。

>[!NOTE]
>
>请在此进行更改之前查看并更新Adobe Campaign中的默认和特定类型规则（如果适用），以确保这些更改正确应用于所有传出通信。 例如，请确保用于选择退出首选项的任何映射都能准确反映收件人的意图／通信选择，并且不会无意中中断关系或事务性消息的投放，如客户订单确认。

如果您选择了&#x200B;**Bidirectional**&#x200B;或&#x200B;**单向(活动到Microsoft Dynamics 365)**&#x200B;选择退出配置，活动选择退出数据将通过工作流定期导出到您的活动SFTP存储区域(请参阅下面的活动SFTP使用情况)。 在您的活动选择退出工作流停止运行的事件中，您需要尽快手动重新启动，以减少错过选择退出同步的可能性。

>[!IMPORTANT]
>
>如果您需要&#x200B;**Bidirectional**&#x200B;或&#x200B;**单向(活动到Microsoft Dynamics 365)**&#x200B;退出配置，您需要向Adobe技术联系人请求在活动实例上设置退出工作流

## 活动SFTP使用

活动SFTP存储需要通过以下使用案例的集成来利用。  您需要确保您的SFTP帐户具有足够的存储容量来适应这些使用情形。 超过许可的SFTP存储容量可能会严重削弱活动、集成和／或SFTP帐户的功能使用。

| 用例 | 说明 |
|---|---|
| 双向和单向(活动到Microsoft Dynamics 365) | 双向和单向(活动到Microsoft Dynamics 365)选择退出数据流将利用活动SFTP存储。 活动工作流会将增量更改导出到SFTP文件夹。 从那里，集成将获取记录和流程。 |
| 退出日志 | 排除集成故障时，连接器的输出日志将很有帮助。 输出日志可以打开／关闭。 |


>[!IMPORTANT]
>
>您负责从SFTP文件夹访问和下载的信息。 如果信息包含个人数据，您有责任遵守任何适用的隐私法律和法规。 [了解详情](#acs-msdyn-manage-privacy)。

## 数据管理

### 现有活动数据

此集成将将联系人和自定义实体从Microsoft Dynamics 365同步到活动。 集成不会修改在集成之外创建的活动记录（即，不是由同步作业创建的），包括集成配置时存在的活动记录。

由于此集成使用活动中的&#x200B;**[!UICONTROL externalId]**&#x200B;字段将活动用户档案记录与Dynamics 365联系人记录同步，因此必须为此活动字段(**[!UICONTROL externalId]**)填充Microsoft Dynamics 365 **[!UICONTROL contactId]**，以获取您希望从Microsoft Dynamics 365同步的记录。  自定义实体也使用Microsoft Dynamics 365唯一ID进行同步。 活动自定义实体需要将此ID属性作为表列包含。 externalId列可用于存储此属性值，但活动自定义实体不需要它。

请记住，Microsoft Dynamics 365仍是真理之源，并且当集成检测到Dynamics 365端的更新时，活动用户档案数据可以被覆盖。  根据您现有的部署，可能需要其他步骤来启用集成；因此，建议您与Adobe技术联系人密切合作。

>[!NOTE]
>
>由于现有客户部署的复杂性，建议您在规划和设置集成时与Adobe技术联系人合作。

### 数据同步频率

该集成采用一种架构，它允许在Microsoft Dynamics 365中发生更新后立即检测更新并将其添加到处理“队列”（即流，而非批处理）。 因此，无需指定数据流运行频率或计划。

这种情况的例外是双向和活动Dynamics 365选择退出数据流。 对于这些选择退出配置，更新的活动记录将通过活动工作流每天导出一次到SFTP，之后，集成工具将读取文件并处理记录。

### 数据使用协议

如果您位于EMEA或APAC地区，则您的某些数据将作为此集成的一部分在美国进行处理。 有关更多信息，请参见[此章节](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

## 护栏和限制

>[!IMPORTANT]
>
>对您执行的某些操作（例如，初始录入记录、重播记录数据等） 可能导致从Microsoft Dynamics 365将大量记录摄取到您的Adobe Campaign实例。 为降低性能问题的风险，建议您停止所有活动流程(例如，无营销活动、无工作流运行等) 直到大量记录被引入活动。

### 自定义实体

[Microsoft Dynamics 365-Adobe Campaign Standard集成](../../integrating/using/d365-acs-get-started.md)支持自定义实体，使Dynamics 365中的自定义实体能够同步到活动中的相应自定义资源。

集成支持链接表和非链接表。

配置自定义实体数据流时，务必注意以下事项：

* 创建和修改活动自定义资源是敏感操作，必须由专家用户执行。
* 对于自定义实体数据流，必须在Dynamics 365中为同步的自定义实体启用更改跟踪。
* 如果在Dynamics 365中，父记录和链接的子记录在接近同一时间创建，则由于集成的并行处理，新的子记录在其父记录之前被写入活动的可能性很小。

* 如果使用&#x200B;**1基数简单链接**&#x200B;选项在活动端链接父记录和子记录，则子记录将保持隐藏且不可访问（通过UI或API），直到父记录到达活动。

* (假定&#x200B;**1基数简单链接**&#x200B;在活动中)如果在Dynamics 365中更新或删除子记录，并且该更改在父记录以活动显示之前写入活动（不太可能，但是可能是远程），则该更新或删除在活动中不会处理，并且将引发错误。 在更新的情况下，需要在Dynamics 365中再次更新相关记录，以同步更新的记录。 在删除的情况下，相关记录需要在活动端单独处理，因为Dynamics 365中不再有要删除或更新的记录。

* 如果您遇到这样的情况，即您认为自己有隐藏的子记录并且无法访问这些记录，则可以将基数链接类型临时更改为&#x200B;**0或1基数简单链接**&#x200B;以访问这些记录。

有关活动自定义资源的更全面概述，请参阅此部分](../../developing/using/key-steps-to-add-a-resource.md)。[

### 集成护栏

在计划使用这一集成时，应考虑以下护栏。 如果您认为超过这些护栏，请咨询Adobe技术代表。

* 您需要许可正确的活动包以支持集成生成的引擎调用量。 超过授权的引擎调用量可能导致活动性能降低。

   使用以下内容帮助评估集成中的引擎调用量：

   * 记录插入（即，新记录）:1个引擎调用
   * 记录删除：1个引擎调用
   * 记录更新：2个引擎调用(如果目标记录与源记录相同，即，如果活动记录没有更改，则只有1个调用)

   在估计整个活动引擎调用量时，必须考虑其他引擎调用来源，包括登陆页、WebApps、JSSP、API、移动应用程序注册等。

   视图活动包信息：https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html

* 该集成最多支持3000万个联系人。

* 标准集成产品最多支持五个自定义实体，每个实体最多50列大小。

* 在实施集成之前，您需要创建并发布自定义资源。

* 链接表时最大表深度为两个（即表1->表2->表3）

* 对Microsoft Dynamic 365数据类型的支持有限。 如果您的数据模型包含简单数据类型以外的数据类型（例如字符串、整数、小数等），则可能需要在使用集成之前更新您的数据模型。

* 如果选择保留活动自定义实体中的现有数据，则需要为集成准备数据。

* Adobe和客户之间可能需要建立入职维护窗口。

* 请注意，集成使用率的显着增加或“高峰”（例如，新记录或更新记录的急剧增加）可能导致数据同步速度变慢。

* 作为集成的一部分，您应完成Microsoft Azure和Dynamics 365中的预集成配置步骤。 请参阅此页上的配置步骤[](../../integrating/using/d365-acs-configure-d365.md)

* 您应将Dynamics 365和活动数据模型集成并加以维护。

### 集成边界

该集成旨在解决Microsoft Dynamics 365与活动之间常见数据移动的一般用例，但它并非旨在解决每个客户特有的每个用例：

* 该集成不会发布任何隐私（例如GDPR）删除。 满足最终用户隐私要求的责任由客户承担；这些请求应在活动(通过Adobe Experience Platform Privacy Service)和Dynamics 365中独立提出。 如果需要，该集成会发出定期删除，以帮助进行数据同步。   有关详细信息，请查阅[隐私部分](#manage-privacy-requests)。

* 用户档案或自定义实体数据不会从活动同步到Dynamics 365，但选择退出信息除外（如果客户配置）。

* 活动订阅管理（即订阅／取消订阅）本机不受支持。

* 不支持在Dynamics 365中编写和触发活动电子邮件活动。

* 集成&#x200B;**不**&#x200B;支持在Dynamics 365和Campaign Standard数据模型之间重构数据。 预计集成将将一个Dynamics 365表同步到一个活动表。
