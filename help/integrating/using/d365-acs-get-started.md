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

在跨渠道通信中激活CRM数据：了解如何将联系人从Microsoft Dynamics 365传递到Adobe Campaign，并将促销活动效果数据（发送、打开、点击和退回）从Adobe Campaign共享到Microsoft Dynamics 365。

此集成需要以下软件版本：

* Microsoft Dynamics 365 for Sales Online，最新版本

* Adobe Campaign Standard，最新版本

>[!CAUTION]
>
>此功能并非作为产品的一部分现成可用。实施需要咨询 Adobe。请联系您的 Adobe 代表以了解更多信息。

## 原则

Adobe Campaign Standard与Microsoft Dynamics 365的集成支持同步CRM系统中所有可用的联系人数据，从而使所有相关联系人数据都可用于促销活动。

相反，当Adobe Campaign Standard中的用户档案与消息交互时，这些数据(例如：发送、打开、点击和退回)会自动流入Microsoft Dynamics 365，以保留完整的营销活动联系记录。

该集成还支持启用 [自定义实体](../../integrating/using/d365-acs-self-service-app-settings.md) 在Dynamics 365中同步到 **自定义资源** 在Campaign中。

此集成旨在支持四个主要用例：

1. 将联系人从Dynamics 365同步到Campaign，以便在营销活动中定位他们
1. 将自定义实体从Dynamics 365同步到Campaign，以便用于分段和个性化
1. 将电子邮件营销事件（发送、打开、点击、退回）从Campaign发送到Dynamics 365，以在Dynamics 365界面中显示到销售存储库
1. 在Dynamics 365和Campaign之间同步选择退出（例如，请勿通过电子邮件）状态，以维护客户隐私首选项。

主要优势包括：

* 销售和营销之间的一致报文传送：Adobe Campaign Standard与Dynamics 365集成使系统能够访问客户洞察信息和电子邮件营销历史，从而允许所有发送给客户的消息共享相同的一致消息。

* 所有潜在客户和客户数据的全面视图：通过将Adobe Campaign Standard与Dynamics 365集成，可以从CRM系统内共享和访问每个联系人的电子邮件营销历史记录。

* 在任何渠道上激活Dynamics 365数据：联系人数据同步到Adobe Campaign后，可通过Campaign的任何在线或离线渠道（包括移动推送、应用程序内、电子邮件或直邮）发送通信。 营销活动“覆盖了您”，而不考虑每个联系人的首选渠道。

>[!CAUTION]
>
>此集成将Dynamics 365视为联系人和自定义实体同步的真实来源。  对同步属性所做的任何更改都应在Dynamics 365中完成，而不应在Adobe Campaign Standard中完成。  如果在Campaign中进行更改，则最终会在同步期间被覆盖。

## 实施Microsoft Dynamics 365集成的关键步骤{#request-and-implement-this-integration}

要配置此集成，您需要执行以下步骤。

请按照以下流程图和流程图详细信息来请求和配置集成。

![](assets/provisioning-wf.png)

流程图详细信息（映射到上述步骤）：

* **步骤1**  — 假定您已拥有或正在购买Microsoft Dynamics 365 for Sales和Adobe Campaign Standard的许可证。
* **步骤2**  — 所有客户均可免费使用标准集成产品；但是，根据您的要求，可能会产生额外费用。 详细了解 [最佳实践和限制](../../integrating/using/d365-acs-notices-and-recommendations.md). 如果新销售订单未包含在原始销售订单中，则需要签署该销售订单，以便利用该集成。
* **步骤3**  — 完成Dynamics 365和Campaign的集成前步骤。 请参阅 [配置此集成](#configure-this-integration).
* **步骤4** -Adobe入门团队将为您提供对集成应用程序用户界面(UI)的访问权限。
* **步骤5**  — 您将能够配置数据映射、替换、过滤器等。 并从集成应用程序UI中测试您的集成。

   >[!IMPORTANT]
   >
   > 如果您需要Dynamics 365选择退出配置的双向或Campaign，则需要向Adobe技术联系人请求在Campaign实例上设置选择退出工作流。 [了解详情](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out)。

### 配置此集成 {#configure-this-integration}

需要为此集成配置三个系统：

* **Adobe Campaign Standard**:您需要设置API访问权限并为集成工具配置新集成。 要实现此目的，请参阅 [本文](../../integrating/using/d365-acs-configure-adobe-io.md).
* **Microsoft Dynamics 365**:您需要创建新的应用程序注册，并使应用程序用户能够使用该集成。  要为此集成配置Microsoft Dynamics 365，请参阅 [本文](../../integrating/using/d365-acs-configure-d365.md).
* **Adobe Campaign Standard与Microsoft Dynamics 365自助应用程序集成**:您将需要按照 [本文](../../integrating/using/d365-acs-self-service-app-control-access.md).

>[!IMPORTANT]
>
>对于每个系统，这些步骤需要由 **管理员**.
>
>本文档中的步骤将指导您完成创建涉及分配权限和/或管理员访问权限的集成/注册。  您有责任确保这些步骤在执行之前符合您的公司政策，并认真执行这些步骤。

### 请求支持

可以通过Adobe客户关怀记录支持票证。

对于集成数据流存在的任何问题，请确保包含以下信息：

* **进程所有者**:工程架构师
* **ES进程ID**:在载入过程中提供
* **流程标题**:Microsoft Dynamics 365 / Adobe Campaign Standard集成
* **问题描述**:问题描述

集成支持范围当前为24x5(星期一至星期五提供，不包括Adobe节假日和休息时间)。
