---
title: Microsoft Dynamics 365 集成快速入门
description: 了解如何开始使用Microsoft Dynamics 365集成
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: fa0f790d-6a4d-4b83-a51f-f565e9545a1a
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '842'
ht-degree: 5%

---

# Microsoft Dynamics 365 集成快速入门

在跨渠道通信上激活您的CRM数据：了解如何将联系人从Microsoft Dynamics 365传递到Adobe Campaign，并将营销活动效果数据（发送、打开、点击和退回）从Adobe Campaign共享回Microsoft Dynamics 365。

此集成需要以下软件版本：

* 仅限Microsoft Dynamics 365 for Sales Online，最新版本

* Adobe Campaign Standard，最新版本

>[!CAUTION]
>
>此功能并非作为产品的一部分现成可用。实施需要咨询 Adobe。请联系您的 Adobe 代表以了解更多信息。
>

## 原则

Adobe Campaign Standard与Microsoft Dynamics 365的集成允许同步CRM系统中所有可用的联系人数据，从而使所有相关联系人数据都可用于营销活动。

相反，当Adobe Campaign Standard中的用户档案与消息交互时，这些数据（例如：发送、打开、点击和退回）会自动流入Microsoft Dynamics 365，以保持联系记录与营销活动完整。

该集成还支持启用 [自定义实体](../../integrating/using/d365-acs-self-service-app-settings.md) (在Dynamics 365中，将同步到 **自定义资源** 在Campaign中。

此集成旨在支持四个主要用例：

1. 将联系人从Dynamics 365同步到Campaign，以便在营销活动中定位他们
1. 将自定义实体从Dynamics 365同步到Campaign，以便用于分段和个性化
1. 将电子邮件营销事件（发送、打开、单击、退回）从Campaign发送到Dynamics 365界面中要显示给销售存储库的Dynamics 365
1. 在Dynamics 365和Campaign之间同步选择退出（例如，不发送电子邮件）状态以维护客户隐私首选项。

主要优势包括：

* 销售与营销之间的消息传送保持一致：Adobe Campaign Standard与Dynamics 365集成使得两个系统都能访问客户洞察和电子邮件营销历史记录，从而允许发送给客户的所有消息都共享相同的一致消息传送。

* 所有潜在客户和客户数据的整体视图：通过将Adobe Campaign Standard与Dynamics 365集成，可以从CRM系统中共享和访问每个联系人的电子邮件营销历史记录。

* 在任意渠道上激活Dynamics 365数据：如果联系人数据同步到Adobe Campaign，则可以通过Campaign在任意在线或离线渠道上发送通信，包括移动推送、应用程序内、电子邮件或直邮。 Campaign“已覆盖”所有内容，无论每个联系人的首选渠道如何。

>[!CAUTION]
>
>此集成将Dynamics 365视为联系人和自定义实体同步的真实来源。  对同步属性的任何更改应在Dynamics 365中完成，而不是在Adobe Campaign Standard中完成。  如果在Campaign中进行了更改，则这些更改最终会在同步期间被覆盖。
>

## 实施Microsoft Dynamics 365集成的关键步骤{#request-and-implement-this-integration}

要配置此集成，您需要执行以下步骤。

请按照下面的流程图和流程图详细信息请求和配置集成。

![](assets/provisioning-wf.png)

流程图详细信息（映射到上述步骤）：

* **步骤1**  — 假定您已拥有或正在获取Microsoft Dynamics 365 for Sales和Adobe Campaign Standard的许可证。
* **步骤2**  — 标准集成产品免费提供给所有客户；但是，根据您的要求，可能会产生额外费用。 了解有关 [最佳实践和限制](../../integrating/using/d365-acs-notices-and-recommendations.md). 如果原始SO中没有包含新销售订单(SO)，则需要签署新销售订单，以便使用该集成。
* **步骤3**  — 完成Dynamics 365和Campaign的集成前步骤。 请参阅 [配置此集成](#configure-this-integration).
* **步骤4** -Adobe入门团队将为您提供集成应用程序用户界面(UI)的访问权限。
* **步骤5**  — 您将能够配置数据映射、替换、筛选器等。 并从集成应用程序UI中测试您的集成。

  >[!IMPORTANT]
  >
  > 如果您需要双向或Campaign to Dynamics 365选择退出配置，则需要向Adobe技术联系人发出请求，才能在Campaign实例上设置选择退出工作流。 [了解详情](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out)。

### 配置此集成 {#configure-this-integration}

需要为此集成配置和配置三个系统：

* **Adobe Campaign Standard**：您需要设置API访问，并为集成工具配置新的集成。 要实现此目的，请参阅 [本文](../../integrating/using/d365-acs-configure-adobe-io.md).
* **Microsoft Dynamics 365**：您需要创建新的应用程序注册并启用应用程序用户以使用集成。  要为此集成配置Microsoft Dynamics 365，请参阅 [本文](../../integrating/using/d365-acs-configure-d365.md).
* **Adobe Campaign Standard与Microsoft Dynamics 365自助应用程序集成**：您需要执行中的步骤 [本文](../../integrating/using/d365-acs-self-service-app-control-access.md).

>[!IMPORTANT]
>
>对于每个系统，这些步骤需要由 **管理员**.
>
>本文档中的步骤将指导您创建涉及分配权限和/或管理员访问权限的集成/注册。  在执行之前，您有责任确保这些步骤符合贵公司的政策，并仔细执行这些政策。
>

### 请求支持

支持工单可由Adobe客户关怀团队记录。

对于集成数据流的任何问题，请确保包括以下信息：

* **进程所有者**：工程架构师
* **ES进程ID**：在新用户引导过程中提供
* **进程标题**：Microsoft Dynamics 365 / Adobe Campaign Standard集成
* **问题描述**：问题描述

集成支持范围当前为24x5(周一至周五提供，不包括Adobe节假日和休息期)。
