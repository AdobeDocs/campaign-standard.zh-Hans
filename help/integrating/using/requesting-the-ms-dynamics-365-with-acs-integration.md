---
solution: Campaign Standard
product: campaign
title: 请求和配置 Microsoft Dynamics 365 集成
description: 了解如何通过Campaign Standard集成请求和配置Microsoft Dynamics 365
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 3%

---


# 请求和配置 Microsoft Dynamics 365 集成

要配置此集成，您需要执行以下步骤。

请按照以下流程图和流程图详细信息请求和配置集成。

![](assets/provisioning-wf.png)

流程图详细信息（映射到上面的步骤）:

* **第1** 步——假定您已经或正在购买Microsoft Dynamics 365的销售许可和Adobe Campaign Standard许可。

* **第2步** -标准集成产品对所有客户免费；但是，可能会根据您的要求支付额外费用(请参 [阅集成护栏和边界](../../integrating/using/ms-dynamics-365-integration-guardrails.md))。需要签署新的销售订单才能利用集成。

* **第3步** -完整Dynamics 365和活动的预集成步骤。请参阅[配置此集成](#configure-this-integration)。

* **步骤4-7**  -Adobe入门小组将在入门过程中与您合作。

## 配置此集成{#configure-this-integration}

需要为此集成配置和配置三个系统：Adobe Campaign Standard、Microsoft Dynamics 365 for Sales和集成工具。 配置文章链接如下。

>[!CAUTION]
>
>对于每个系统，这些步骤需要由管理员执行。
>
>以下文章中的步骤将指导您完成创建涉及分配权限和／或管理员访问权限的集成／注册。  您有责任确保这些步骤在执行前符合您的公司政策，并仔细执行。

在ADOBE CAMPAIGN中，您需要设置API访问并为集成工具配置新集成。 要实现此目的，请参阅[本文](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)。

在MICROSOFT DYNAMICS 365中，您需要创建新的应用程序注册，并使应用程序用户能够使用该集成。  要为此集成配置Microsoft Dynamics 365，请参阅[本文](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)。

您需要与Adobe入门小组合作，为入口、出口和退出数据流设置配置。


## 请求支持

支持票证可以像往常一样通过Adobe自定义服务记录；客户关怀将根据需要引入支持人员。

对于集成数据流中的任何问题，请确保将报表包包含在问题描述中以及以下信息：

* **流程所有者**:工程架构师

* **ES进程ID**:在入门过程中提供

* **流程标题**:Dynamics 365/Adobe Campaign Standard集成

* **问题描述**:问题说明

集成支持覆盖期目前为24x5(周一至周五提供，不包括Adobe假期和休息期)。