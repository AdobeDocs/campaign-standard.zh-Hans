---
title: 关于 Campaign-Audience Manager 或 People 核心服务集成
description: 通过Audience Manager/People核心服务集成，您可以在不同的Adobe Experience Cloud解决方案中共享受众或区段。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: e8b96c66-82f7-4adb-88b2-b7e0f7c4a96f
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 18%

---

# 关于 Campaign-Audience Manager 或 People 核心服务集成{#about-campaign-audience-manager-or-people-core-service-integration}

>[!CAUTION]
>
>根据交换的数据，在Adobe Campaign中导入受众可能会受到法律限制。

Adobe Campaign允许您与其他Adobe Experience Cloud应用程序交换和共享受众/区段。 通过将&#x200B;**Adobe Campaign**&#x200B;与&#x200B;**People核心服务**（也称为&#x200B;**Profiles &amp; Audiences核心服务**）或Adobe Audience Manager集成，您可以：

* 从不同的Adobe Experience Cloud解决方案导入受众/区段到Adobe Campaign。 可以从Adobe Campaign中的&#x200B;**[!UICONTROL Audiences]**&#x200B;菜单导入受众。
* 将受众导出为共享受众/区段。 您可在所用的不同 Adobe Experience Cloud 解决方案中使用这些受众。在工作流中定位活动后，可使用&#x200B;**[!UICONTROL Save audience]**&#x200B;活动导出受众。

集成支持两种类型的Adobe Experience Cloud ID：

* **访客ID**：此类型的ID允许您协调Adobe Experience Cloud访客与Adobe Campaign配置文件。 通过Adobe IMS启用连接后，Marketing Cloud访客ID服务即会激活，这将替换Adobe Campaign使用的永久Cookie。 这允许您识别访客，然后将其链接到用户档案。
  <br>访客ID在配置文件单击通过Adobe Campaign发送的电子邮件后立即链接到配置文件：
   * 如果配置文件已具有访客ID，则该配置文件的浏览器数据允许Adobe Campaign进行恢复，并自动将配置文件链接到访客ID。
   * 如果未找到访客ID，则会创建一个新的ID。 此访客ID存储在配置文件跟踪日志中。

  随后，该ID将由具有相同CNAME的其他Adobe Marketing Cloud应用程序识别。

* **声明的ID**：此类型的ID允许您协调任何类型的数据与Adobe Campaign数据库中的元素。 它在Adobe Campaign中表示为预定义的合并关键项。 交换数据时，Adobe Campaign数据库标识符将进行哈希处理。 随后，这些经过哈希处理的ID将与导入或导出中涉及的Adobe Marketing Cloud受众的经过哈希处理的ID进行比较。
  <br>此集成支持常规声明的ID、散列声明的ID和加密声明的ID。

  >[!NOTE]
  >
  >声明的 ID 数据源现在还可以与 People 核心服务集成一起使用。
  >
  >如果您使用 People 核心服务集成，并想要添加 Audience Manager 集成，则需要 Adobe Audience Manager 顾问的帮助，以避免在 Adobe Audience Manager 环境中转换为使用此声明的 ID 数据源时收集的所有 ID 同步丢失。


  加密允许您通过指定加密算法，使用声明的ID共享数据源（例如PII）中的加密数据。

  例如，利用解密加密电子邮件地址或短信号码的功能，您还可以向用户发送触发消息，即使Adobe Campaign数据库中不存在用户的档案。

下图详细说明此集成的工作方式。 在此，AAM表示Adobe Audience Manager，ACS表示Adobe Campaign Standard。

![](assets/aam_diagram.png)
