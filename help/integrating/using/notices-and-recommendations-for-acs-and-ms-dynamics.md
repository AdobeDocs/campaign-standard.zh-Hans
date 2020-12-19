---
solution: Campaign Standard
product: campaign
title: 活动和Microsoft Dynamics 365数据管理
description: 了解Campaign Standard和Microsoft Dynamics 365如何管理常见数据
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1448'
ht-degree: 1%

---


# 在活动和Microsoft Dynamics 365之间管理数据

## 单向同步的真相来源

对于联系人和自定义实体同步，此集成将Dynamics 365视为真理源。  对同步属性所做的任何更改应在Dynamics 365中进行，而不是在活动中。  如果更改是在活动中进行的，则在同步过程中最终可能会在活动中覆盖这些更改，因为同步是单向的。

## 联系人删除

如果需要，可以将集成配置为在Dynamics 365中删除联系人时向活动发出用户档案删除调用，以帮助保持数据完整性。

但是，用户档案删除与隐私删除不同。 活动中的隐私删除将删除活动用户档案记录和相关日志条目；而常规用户档案删除只会删除ACS用户档案记录，而保留活动日志中的残留内容。

如果在集成中启用用户档案删除功能，则需要执行其他步骤才能正确处理数据主体隐私请求。 请参阅下面[部分中的步骤。](#manage-privacy-requests)

## 隐私

### 管理隐私请求{#manage-privacy-requests}

此集成旨在在Microsoft Dynamics 365和Adobe Campaign Standard之间传输最终用户数据（包括但不限于个人信息，如果其包含在最终用户数据中）。 作为公司管理者，您有责任遵守适用于您收集和使用个人数据的任何隐私法律和法规。

该集成不会发布任何数据主体隐私（例如，GDPR）删除或处理任何其他隐私请求（退出除外）。 处理隐私请求时，您应在Dynamics 365和活动(通过Adobe Experience Platform Privacy Service)中单独执行。

如果已将集成配置为在Dynamics 365中删除联系人时向活动发出定期用户档案删除调用，则应遵循以下步骤。 确保在此过程中未对相关记录进行任何更新。

1. 向[Adobe Experience Platform Privacy Service](https://www.adobe.io/apis/experiencecloud/gdpr.html)发出隐私删除请求

1. 监视请求，直到它成功完成

1. 验证记录不再在活动实例中

1. （不久之后）在Dynamics 365中删除问题隐私

1. 验证记录是否已从两个系统中删除

下面是帮助指导您在每个系统中实施访问和／或删除隐私相关请求的链接：

* [Microsoft Dynamics 365](https://docs.microsoft.com/en-us/microsoft-365/compliance/gdpr-dsr-dynamics365?toc=/microsoft-365/enterprise/toc.json)

* [Adobe Campaign Standard](https://www.adobe.io/apis/experiencecloud/gdpr/docs.html)


### 隐私和链接资源{#privacy-linked-resources}

如果任何活动自定义资源记录包含适用于客户使用活动的个人信息，则此类记录应链接到相应的活动用户档案记录（直接或通过其他自定义资源），以便与用户档案记录相关的隐私删除也可以删除包含个人信息的链接自定义资源记录；必须配置实体之间的链接和删除选项，以启用链接记录的类层叠删除。 个人信息不应输入到未链接到用户档案的自定义资源中。

了解如何映射活动资源和Dynamics 365实体[，请参阅本节](../../integrating/using/map-campaign-custom-resources-and-dynamics-365-custom-entities.md)。

## 选择退出

由于Dynamics 365和活动之间的选择退出属性存在差异，以及每个客户的业务要求存在差异，因此选择退出映射已被留作客户完成的一项练习。  务必确保在系统之间正确映射退出功能，以便最终用户选择退出首选项得以保持，并且他们不会通过已选择退出的渠道接收通信。

请注意，只有带有“不再通过电子邮件联系”前缀的活动属性（例如，不再通过电子邮件联系）或CCPA选择退出的特定属性才能用于选择退出映射。 [了解详情](../../developing/using/datamodel-profile.md)。在Dynamics 365中，大多数选择退出字段带有“donot”前缀；但是，如果数据类型兼容，您也可以使用其他属性进行退出。

设置集成时，您将有机会指定您的企业需要的退出配置：

* Dynamics 365是退出选择的真相来源：退出属性将沿一个方向从Dynamics 365同步到活动
* 活动是选择退出的真相来源：退出属性将沿一个方向从活动同步到Dynamics 365
* Dynamics 365 AND活动既是真理的源泉：退出属性将在活动和Dynamics 365之间双向同步

或者，如果您有单独的过程来管理系统之间的退出同步，则可禁用集成的退出数据流。

双向选择退出配置使用逻辑确定要写入两个系统的值。 该逻辑比较两个系统之间的时间戳(Dynamics 365中的记录级别更改，活动中的属性级别更改)以确定哪个系统占上风。 如果活动包含更新的时间戳，则活动值优先。 如果Dynamics 365包含更新的时间戳，或者如果时间戳相等，则opt-out=TRUE将获胜（假定其中一个值为TRUE）。

>[!NOTE]
>
>请在此进行更改之前查看并更新Adobe Campaign中的默认和特定类型规则（如果适用），以确保这些更改正确应用于所有传出通信。 例如，请确保用于选择退出首选项的任何映射都能准确反映收件人的意图／通信选择，并且不会无意中中断关系或事务性消息的投放，如客户订单确认。

如果您选择了Dynamics 365选择退出配置的双向或活动,活动选择退出数据将通过工作流定期导出到您的活动SFTP存储区域(请参阅下面的活动SFTP使用情况)。 在您的活动选择退出工作流停止运行的事件中，您需要尽快手动重新启动，以减少错过选择退出同步的可能性。

## 活动SFTP使用

活动SFTP存储需要通过以下使用案例的集成来利用。  您需要确保您的SFTP帐户具有足够的存储容量来适应这些使用情形。  超过许可的SFTP存储容量可能会严重削弱活动、集成和／或SFTP帐户的功能使用。

| 用例 | 说明 |
|---|---|
| 初始数据加载 | 需要将超过500k记录的Dynamics 365表导出到活动SFTP存储，然后通过工作流导入。 此后，集成将使用API进行增量更新。 |
| 双向退出与Dynamics 365单向退出活动 | 双向选择退出和活动到Dynamics 365单向选择退出数据流将利用活动SFTP存储。 ACS工作流会将增量更改导出到SFTP文件夹。 从那里，集成将获取记录和流程。 |
| 灾难恢复 | 在发生系统灾难的不可能事件下，将遵循“初始数据加载”用例，将增量更新提供给丢失的活动。 |

## 现有活动数据

此集成将将联系人和自定义实体从Dynamics 365同步到活动。 集成不会修改在集成之外创建的活动记录（即，不是由同步作业创建的），包括集成配置时存在的活动记录。

由于此集成使用活动中的&#x200B;**[!UICONTROL externalId]**&#x200B;字段将活动用户档案记录与Dynamics 365联系人记录同步，因此必须为此活动字段(**[!UICONTROL externalId]**)填充Dynamics 365 **[!UICONTROL contactId]**，以便从Dynamics 365同步记录。  自定义实体也使用Dynamics 365唯一ID进行同步。 活动自定义实体需要将此ID属性作为表列包含。 externalId列可用于存储此属性值，但活动自定义实体不需要它。

请记住，Dynamics 365仍是真理之源，并且当集成检测到Dynamics 365端的更新时，活动用户档案数据可以被覆盖。  根据您现有的部署，可能需要其他步骤来启用集成；因此，建议您与Adobe技术联系人密切合作。

>[!NOTE]
>
>由于现有客户部署的复杂性，建议您在规划和设置集成时与Adobe技术联系人合作。

## 数据同步频率

该集成采用一种架构，它允许在Dynamics 365中发生更新后立即检测更新并将其添加到处理“队列”（即流，而非批处理）。 因此，无需指定数据流运行频率或计划。

Dynamics 365的双向和活动选择退出数据流。 对于这些选择退出配置，更新的ACS记录每天通过ACS工作流程导出到SFTP，然后，集成工具读取文件并处理记录。

## 数据使用协议

如果您位于EMEA或APAC地区，则您的某些数据将作为此集成的一部分在美国进行处理。 有关更多信息，请参见[此章节](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。
