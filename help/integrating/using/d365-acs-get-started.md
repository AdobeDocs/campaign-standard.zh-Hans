---
title: Microsoft Dynamics 365 集成快速入门
description: 了解如何开始使用Microsoft Dynamics 365集成
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: tm+mt
source-git-commit: 93e4310c606cb39a1071b8e20d88978839007765
workflow-type: tm+mt
source-wordcount: '842'
ht-degree: 5%

---


# Microsoft Dynamics 365 集成快速入门

在跨渠道通信中激活CRM数据：了解如何将联系人从Microsoft Dynamics 365传递到Adobe Campaign，以及将活动性能数据（发送、打开、单击和弹回）从Adobe Campaign传回Microsoft Dynamics 365。

此集成需要以下软件版本：

* 仅限Microsoft Dynamics 365 for Sales Online，最新版本

* Adobe Campaign Standard，最新版本

>[!CAUTION]
>
>此功能并非作为产品的一部分现成可用。实施需要咨询 Adobe。请联系您的 Adobe 代表以了解更多信息。


## 原则

Adobe Campaign Standard与Microsoft Dynamics 365的集成支持CRM系统中所有可用联系人数据的同步，使所有相关联系人数据都可用于活动活动。

相反，当Adobe Campaign Standard内的用户档案与消息交互时，这些数据(例如：发送、打开、点击和弹回)会自动流入Microsoft Dynamics 365，以保存包含营销活动的联系人记录。

该集成还支持使Dynamics 365中的[自定义实体](../../integrating/using/d365-acs-self-service-app-settings.md)与活动中相应的&#x200B;**自定义资源**&#x200B;同步。

此集成旨在支持四个主要用例：

1. 将联系人从Dynamics 365同步到活动，以便在营销活动中定位
1. 将自定义实体从Dynamics 365同步到活动，以便用于细分和个性化
1. 将电子邮件营销事件（发送、打开、点击、弹回）从活动发送到Dynamics 365，以显示到Dynamics 365界面中的销售存储库
1. 同步Dynamics 365和活动之间的退出（例如，不要通过电子邮件发送）状态，以保持客户隐私首选项。

主要优势包括：

* 销售和营销之间的一致消息传递：Adobe Campaign Standard与Dynamics 365集成使系统能够访问客户洞察和电子邮件营销历史，从而使所有发送给客户的消息能够共享相同的一致消息。

* 全面视图所有潜在客户和客户数据：通过将Adobe Campaign Standard与Dynamics 365集成，可以从CRM系统内共享和访问每个联系人的电子邮件营销历史。

* 在任何渠道上激活Dynamics 365数据：通过将联系人数据同步到Adobe Campaign，可以通过活动（包括移动推送、应用程序内、电子邮件或直邮）在任何在线或离线渠道上发送通信。 活动“覆盖了您”，而不管每个联系人的首选渠道。

>[!CAUTION]
>
>此集成将Dynamics 365视为联系和自定义实体同步的真伪源。  对同步属性的任何更改应在Dynamics 365中完成，而不应在Adobe Campaign Standard中。  如果更改是在活动中进行的，则它们最终可能会在同步过程中被覆盖。


## 实施Microsoft Dynamics 365集成{#request-and-implement-this-integration}的关键步骤

要设置此集成，您需要执行以下步骤。

请按照以下流程图和流程图详细信息请求和配置集成。

![](assets/provisioning-wf.png)

流程图详细信息（映射到上面的步骤）：

* **第1** 步 — 假定您已拥有或正在购买适用于Microsoft Dynamics 365（销售版）和Adobe Campaign Standard的许可证。
* **第2步**  — 标准集成产品对所有客户免费；但是，根据您的要求，可能会产生额外成本。了解有关[最佳实践和限制的更多信息](../../integrating/using/d365-acs-notices-and-recommendations.md)。 如果原始SO中未包含新销售订单(SO)，则需要签署新销售订单以利用该集成。
* **第3步**  — 完成Dynamics 365和活动的预集成步骤。请参阅[配置此集成](#configure-this-integration)。
* **第4步** -Adobe入门小组将为您提供对集成应用程序用户界面(UI)的访问权限。
* **第5步**  — 您将能够配置数据映射、替换、过滤器等。并在集成应用程序UI中测试集成。

   >[!IMPORTANT]
   >
   > 如果您需要双向或活动到Dynamics 365退出配置，您需要向Adobe技术联系人发出请求，以便在您的活动实例上设置退出工作流。 [了解详情](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out)。

### 配置此集成{#configure-this-integration}

需要为此集成配置和配置三个系统：

* **Adobe Campaign Standard**:您需要设置API访问并为集成工具配置新集成。要实现此目的，请参阅[本文](../../integrating/using/d365-acs-configure-adobe-io.md)。
* **Microsoft Dynamics 365**:您需要创建新的应用程序注册，并使应用程序用户能够使用该集成。要为此集成配置Microsoft Dynamics 365，请参阅[本文](../../integrating/using/d365-acs-configure-d365.md)。
* **Adobe Campaign Standard与Microsoft Dynamics 365自助服务应用程序集成**:您需要按照本文中的步 [骤操作](../../integrating/using/d365-acs-self-service-app-control-access.md)。

>[!IMPORTANT]
>
>对于每个系统，这些步骤需要由&#x200B;**管理员**&#x200B;执行。
>
>本文档中的步骤将指导您完成创建集成/注册的过程，包括分配权限和/或管理员访问权限。  您有责任确保这些步骤在执行前符合您的公司策略，并谨慎执行。


### 请求支持

支持票证可以通过Adobe客户关怀记录。

对于集成数据流的任何问题，请确保包括以下信息：

* **流程所有者**:工程设计师
* **ES进程ID**:在入职过程中提供
* **流程标题**:Microsoft Dynamics 365/Adobe Campaign Standard集成
* **问题描述**:问题说明

集成支持范围目前为24x5(星期一至星期五提供，不包括Adobe假日和休息时段)。
