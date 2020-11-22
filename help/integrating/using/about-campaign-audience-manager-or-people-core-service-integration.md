---
solution: Campaign Standard
product: campaign
title: 关于 Campaign-Audience Manager 或 People 核心服务集成
description: 通过Audience Manager/人员核心服务集成，您可以在不同的Adobe Experience Cloud解决方案中共享受众或细分。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 5%

---


# 关于 Campaign-Audience Manager 或 People 核心服务集成{#about-campaign-audience-manager-or-people-core-service-integration}

>[!CAUTION]
>
>根据交换的受众，以Adobe Campaign导入数据可能受到法律限制。

Adobe Campaign允许您与不同的Adobe Experience Cloud应用程序交换和共享受众/细分。 将 **Adobe Campaign****与People核心服务** (也称为 **用户档案和受众核心服务**)或Adobe Audience Manager集成，使您能够：

* 将受众/细分从不同的Adobe Experience Cloud解决方案导入Adobe Campaign。 受众可以从菜单中 **[!UICONTROL Audiences]** 以Adobe Campaign导入。
* 将受众导出为共享受众/区段。 这些受众可用于您使用的不同Adobe Experience Cloud解决方案。 受众可以在工作流中定位活动后使用活动导 **[!UICONTROL Save audience]** 出。

集成支持两种类型的Adobe Experience CloudID:

* **访客ID**:此类型的ID允许您协调Adobe Experience Cloud访客与Adobe Campaign用户档案。 一旦通过AdobeIMS启用连接，Marketing Cloud访客ID服务即被激活，这将取代Adobe Campaign使用的永久cookie。 这允许您识别访客，然后将其链接到用户档案。
   <br>访客ID在用户档案单击通过Adobe Campaign发送的电子邮件后立即链接到用户档案:
   * 如果用户档案已经有访客ID，则用户档案的浏览器数据允许Adobe Campaign恢复并自动将用户档案链接到访客ID。
   * 如果找不到访客ID，则会创建新ID。 此访客ID存储在用户档案跟踪日志中。

   ID随后将由具有相同CNAME的其他Adobe Marketing Cloud应用程序识别。

* **声明的ID**:此类型的ID允许您将任何类型的数据与Adobe Campaign库中的元素进行协调。 它以Adobe Campaign表示为预定义合并关键项。 交换Adobe Campaign时，对数据库标识符进行散列处理。 然后，将这些散列ID与进口或出口涉及的Adobe Marketing Cloud受众的散列ID进行比较。
   <br>此集成支持常规声明ID、散列声明ID和加密声明ID。

   >[!CAUTION]
   >
   >声明的ID只能与Adobe Audience Manager一起使用。 没有声明的ID，它将无法工作。

   加密允许您通过指定加密算法，使用声明的ID在数据源（例如PII）中共享加密数据。

   例如，利用解密加密电子邮件地址或SMS号的能力，您还可以向用户发送触发消息，即使Adobe Campaign用户档案库中不存在触发消息。

下图详细说明此集成的工作方式。这里，AAM代表Adobe Audience Manager和Adobe Campaign Standard。

![](assets/aam_diagram.png)