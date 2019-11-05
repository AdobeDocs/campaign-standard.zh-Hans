---
title: 关于 Campaign-Audience Manager 或 People 核心服务集成
description: 通过Audience Manager/People核心服务集成，您可以在不同的Adobe Experience cloud解决方案中共享受众或细分。
page-status-flag: 从未激活
uuid: 39e3c78e-cccd-4823-afe9-abc7f8aef034
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 集成
content-type: 参考
topic-tags: 使用Campaign和Audience manager或People核心服务
discoiquuid: bf718329-f181-46f7-80a2-b525a8dee46d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 关于 Campaign-Audience Manager 或 People 核心服务集成{#about-campaign-audience-manager-or-people-core-service-integration}

Adobe Campaign允许您使用不同的Adobe Experience cloud应用程序交换和共享受众／细分。 将 **Adobe Campaign****与People核心服务** (也称为Profiles &amp; Audiences核心服务 ****)或Adobe Audience manager集成后，您可以：

* 将不同Adobe Experience cloud解决方案中的受众／细分导入Adobe Campaign。 可以从Adobe Campaign的菜 **[!UICONTROL Audiences]** 单导入受众。
* 将受众导出为共享的受众／区段。 这些受众可用于您使用的不同Adobe Experience cloud解决方案。 在工作流中定位活动后，可以使用活动导出受 **[!UICONTROL Save audience]** 众。

集成支持两种类型的Adobe Experience Cloud ID:

* **访客ID**:此类型的ID允许您将Adobe Experience cloud访客与Adobe Campaign配置文件进行协调。
* **声明的ID**:此类型的ID允许您将任何类型的数据与Adobe Campaign数据库中的配置文件进行协调。 此集成支持常规声明ID、散列声明ID和加密声明ID。 要了解有关有效性的 **[!UICONTROL Declared ID]** 更多信息，请参阅此 [页面](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md)。

   加密允许您通过指定加密算法，使用声明的ID在数据源（例如PII）中共享加密数据。

   例如，利用解密加密的电子邮件地址或SMS号码的功能，您还可以向用户发送触发消息，即使Adobe Campaign数据库中不存在其配置文件也是如此。

>[!CAUTION]
>
>根据交换的数据，在Adobe Campaign中导入受众可能会受到法律限制

