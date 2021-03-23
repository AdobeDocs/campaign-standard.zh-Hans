---
solution: Campaign Standard
product: campaign
title: 关于 Campaign-Audience Manager 或 People 核心服务集成
description: 通过Audience Manager/人员核心服务集成，您可以在不同的Adobe Experience Cloud解决方案中共享受众或细分。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: 触发器
role: 数据架构师
level: 中间
translation-type: tm+mt
source-git-commit: a6272db76fbfca7b9ebcc3734368f7c032b234af
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 4%

---


# 关于 Campaign-Audience Manager 或 People 核心服务集成{#about-campaign-audience-manager-or-people-core-service-integration}

>[!CAUTION]
>
>根据交换的受众，在Adobe Campaign中导入数据可能受到法律限制。

Adobe Campaign允许您与不同的Adobe Experience Cloud应用程序交换和共享受众/细分。 将&#x200B;**Adobe Campaign**&#x200B;与&#x200B;**People核心服务**(也称为&#x200B;**用户档案和受众核心服务**)或Adobe Audience Manager集成，您可以：

* 将受众/区段从不同的Adobe Experience Cloud解决方案导入Adobe Campaign。 受众可以从Adobe Campaign的&#x200B;**[!UICONTROL Audiences]**&#x200B;菜单中导入。
* 将受众导出为共享受众/区段。 这些受众可用于您使用的不同Adobe Experience Cloud解决方案。 受众可在工作流中的定位活动后使用&#x200B;**[!UICONTROL Save audience]**&#x200B;活动导出。

集成支持两种类型的Adobe Experience Cloud ID:

* **访客ID**:此类型的ID允许您协调Adobe Experience Cloud访客与Adobe Campaign用户档案。一旦通过Adobe IMS启用连接，将激活Marketing Cloud访客ID服务，这将替换Adobe Campaign使用的永久Cookie。 这允许您识别访客，然后将其链接到用户档案。
   <br>访客ID在用户档案单击通过Adobe Campaign发送的电子邮件后立即链接到用户档案:
   * 如果用户档案已经有访客ID，则用户档案的浏览器数据允许Adobe Campaign恢复并自动将用户档案链接到访客ID。
   * 如果未找到访客ID，则会创建新ID。 此访客ID存储在用户档案跟踪日志中。

   然后，具有相同CNAME的其他Adobe Marketing Cloud应用程序将识别该ID。

* **声明的ID**:此类型的ID允许您将任何类型的数据与Adobe Campaign数据库中的元素进行协调。它在Adobe Campaign中表示为预定义合并关键项。 在交换数据时，Adobe Campaign数据库标识符被散列化。 然后，将这些哈希ID与导入或导出中涉及的Adobe Marketing Cloud受众的哈希ID进行比较。
   <br>此集成支持常规声明ID、散列声明ID和加密声明ID。

   >[!NOTE]
   >
   >声明的ID数据源现在还可以与People核心服务集成一起使用。
   >
   >如果您使用People核心服务集成并想添加Audience Manager集成，则需要Adobe Audience Manager顾问的帮助，以避免在Adobe Audience Manager上下文中转换到使用此Declared ID数据源时收集的所有ID同步丢失。


   加密允许您通过指定加密算法，使用声明的ID在数据源（例如PII）中共享加密数据。

   例如，利用解密加密电子邮件地址或SMS号的能力，您还可以向用户发送触发消息，即使其用户档案在Adobe Campaign数据库中不存在也是如此。

下图详细说明此集成的工作方式。此处，AAM代表Adobe Audience Manager,ACS代表Adobe Campaign Standard。

![](assets/aam_diagram.png)