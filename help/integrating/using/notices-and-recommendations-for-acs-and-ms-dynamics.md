---
title: “与Campaign Standard和Microsoft Dynamics 365合作：声明与建议”
description: 了解如何使用Campaign Standard和Microsoft Dynamics的注意事项和建议365
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 620be6615d162672948c3dccdae2752b8c999c47

---


# 使用Campaign Standard和Microsoft Dynamics 365:通知和建议

## 区域支持

此集成在北美、欧洲、中东和非洲地区和亚太地区提供。

如果您位于EMEA或APAC地区，则您的某些数据将作为此集成的一部分在美国进行处理。 有关更多信息，请参见[此部分](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

## 单向联系人同步的真相来源

对于“联系人”和自定义实体同步，此集成将Dynamics 365视为真相的来源。对同步属性的任何更改应在Microsoft Dynamics 365中完成，而不是在Adobe Campaign标准版中完成。如果在活动中进行更改，则在同步过程中最终会在活动中覆盖这些更改，因为同步是单向的。  此外，“联系人同步”设计为拉取所有“联系人”记录，无论这些记录在Microsoft Dynamics 365中标记为活动或非活动状态。

## 管理隐私请求

此集成旨在在Microsoft Dynamics 365和Adobe Campaign标准版之间传输最终用户数据(包括但不限于个人信息（如果这些信息包含在您的最终用户数据中）)。  作为数据管理者，您的公司有责任遵守适用于您收集和使用个人数据的任何隐私法律和法规。

对于此集成，您必须独立处理每个系统中的每个数据主体请求，以便在两个数据库中反映所做的更改。 更改应首先在Microsoft Dynamics 365中执行，然后在Adobe Campaign标准中执行。 唯一的例外是，当在Dynamics 365中删除联系人时，将与隐私相关的删除请求添加到Campaign Standard中的“隐私工具”队列。

以下是帮助指导您在每个系统中实施访问和／或删除隐私相关请求的链接：

* [Microsoft Dynamics 365](https://docs.microsoft.com/en-us/microsoft-365/compliance/gdpr-dsr-dynamics365?toc=/microsoft-365/enterprise/toc.json)

* [Adobe Campaign标准](https://www.adobe.io/apis/experiencecloud/gdpr/docs.html)

## 删除联系人

由于Dynamics 365是真理的源头，Dynamics 365中的接触删除将反映在活动中。

在Dynamics 365中删除联系人后，集成会在活动隐私请求／工具屏幕中排队等待与隐私相关的删除请求。  如果您已经为隐私相关删除请求禁用了两步流程，则活动会为您处理删除。

但是，如果启用了两步流程，您需要在隐私技术工作流运行后进入“隐私请求／工具”屏幕，并确认是否可以删除记录。  只有这样，活动才会处理删除。

有关详细信息，请参阅 [如何在Adobe Campaign标准版中执行与隐私相关的删除请求](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/privacy/execute-privacy-requests.html)

>[!CAUTION]
>
>如果您在活动中为隐私请求启用了两步流程，则Dynamics 365中的删除不会自动反映在活动中。  您需要进入活动隐私请求屏幕以确认删除。

>[!NOTE]
>
>此集成使用外部ID（即Dynamics 365联系人ID）作为记录/用户档案标识符创建请求。

## 选择退出

由于Dynamics 365和活动之间的选择退出属性不同，以及每个客户的业务需求不同，选择退出映射被留作客户完成的练习。务必确保在系统之间正确映射退出选项，以便保持最终用户退出首选项，并且他们不会通过已选择退出的渠道获得通信。

请注意，只有具有“blackList”前缀（例如blackListEmail）的活动属性或CCPA选择退出的特定属性才能用于选择退出映射。  在Dynamics 365中，大多数退出字段都有“doNot”前缀；但是，如果数据类型兼容，您还可以利用您为退出目的创建的自定义属性。

在配置集成时，您将有机会指定业务需要的退出配置：

* Dynamics 365是退出选择的真相：退出属性将在从Dynamics 365到Campaign Standard的一个方向上同步
* Campaign Standard是选择退出的真相来源：退出属性将在从Campaign Standard到Dynamics 365的一个方向上同步
* 动态365和Campaign Standard都是真理的源泉：选择退出属性将在Campaign Standard和Dynamics 365之间双向同步

按照 [Unifi用户指南中的置备后说](https://drive.google.com/drive/folders/16seHF45e6bFxHX15zWLqFLEXymCuA_wn) 明，正确映射这些值。

双向选择退出配置使用逻辑确定要写入两个系统的值。  该逻辑比较两个系统之间的时间戳(Dynamics 365中的记录级别更改，活动中的属性级别更改)以确定哪个系统占上风。  如果活动包含较新的时间戳，则活动值优先。  如果Dynamics 365包含更新的时间戳，或者如果时间戳相等，则opt-out=TRUE将成功（假定其中一个值为TRUE）。

**根据加利福尼亚州消费者保护法(CCPA)和类似法律选择退出。**

双向选择退出配置功能目前不能支持符合CCPA和／或其他现成数据隐私法的某些法定要求。 必须遵守CCPA或与选择退出相关的类似法律要求的客户负责实施自己的第三方解决方案以执行双向同步。

>[!NOTE]
>
>如果公司不需要双向退出支持，建议您选择单向退出选项。

>[!NOTE]
>
>请查看并在适当时更新Adobe Campaign中的默认和特定类型规则，然后在此处进行更改，以确保这些更改正确应用于所有传出通信。 例如，请确保到选择退出首选项的任何映射准确反映了收件人的意图／通信选择，并且不会因疏忽而中断关系或事务性消息（如客户订单确认）的投放。

## 现有活动数据

此集成将将联系人和自定义实体从Dynamics 365同步到活动。 在集成之外创建的活动记录（即，不是由同步作业创建的）不会被集成所影响，包括集成配置时存在的活动记录。

由于此集成使用Campaign Standard中的字段将活动用户档案记录与Dynamics 365联系人记录同步，因此必须用Dynamics 365填充此活动字段( **[!UICONTROL externalId]****[!UICONTROL externalId]****[!UICONTROL contactId]** )，才能将您希望从Dynamics 365同步的记录填入Dynamics 365。  自定义实体还需要正确显示并填充此字段以保持同步。  但是，请记住，Dynamics 365仍将是真相的来源，并且当集成检测到Dynamics 365端的更新时，活动用户档案数据可能会被覆盖。  根据您现有的部署，可能需要其他步骤来启用集成；因此，建议您与Adobe技术联系人密切合作。

>[!NOTE]
>
>由于现有客户部署的复杂性，建议您在规划和设置集成时与Adobe技术联系人合作。
