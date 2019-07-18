---
title: 关于Campaign-Audience Manager或People核心服务集成
seo-title: 关于Campaign-Audience Manager或People核心服务集成
description: 关于Campaign-Audience Manager或People核心服务集成
seo-description: 通过Audience Manager/People核心服务集成，您可以共享不同Adobe Experience Cloud解决方案中的受众或细分。
page-status-flag: 从未激活
uuid: 39e3c78e-ccd-4823-afe9-abc7 f8 aef034
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 集成
content-type: reference
topic-tags: publishing-with-campaign-and-operators-manager-or-ople-core-service
discoiquuid: bf718329-f181-46f7-80a2-b525 a8 dee46 d
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# About Campaign-Audience Manager or People core service integration{#about-campaign-audience-manager-or-people-core-service-integration}

Adobe Campaign允许您使用不同的Adobe Experience Cloud应用程序交换和共享受众/细分。Integrating **Adobe Campaign** with **People core service** (also known as **Profiles &amp; Audiences core service**) or Adobe Audience Manager allows you to:

* 将来自不同Adobe Experience Cloud解决方案的受众/细分导入Adobe Campaign。Audiences can be imported from the **[!UICONTROL Audiences]** menu in Adobe Campaign.
* 将受众导出为共享受众/细分。这些受众可用于您使用的不同Adobe Experience Cloud解决方案。Audiences can be exported after targeting activities in a workflow, using the **[!UICONTROL Save audience]** activity.

集成支持两种类型的Adobe Experience Cloud ID：

* **访客ID**：此类型的ID允许您将Adobe Experience Cloud访客与Adobe Campaign配置文件协调。
* **声明的ID**：此类型的ID允许您将任何类型的数据与Adobe Campaign数据库中的配置文件协调。此集成支持定期声明的ID、散列声明的ID和已加密的声明ID。

   加密允许您通过指定加密算法在数据源(例如PII)中共享加密数据(例如PII)。

   例如，由于能够解密加密的电子邮件地址或SMS编号，即使Adobe Campaign数据库中不存在其配置文件，您也可以向用户发送触发的消息。

>[!CAUTION]
>
>根据交换的数据，在Adobe Campaign中导入受众可能会受到法律限制

