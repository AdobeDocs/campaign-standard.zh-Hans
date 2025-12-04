---
title: 关于 Adobe Experience Platform Data Connector
description: 管理XDM架构以使您的Campaign Standard数据可在Adobe Experience Platform上使用。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Experienced
exl-id: f4fcf256-e030-4d7b-b4b7-2448acc2ae1c
hide: true
hidefromtoc: true
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '706'
ht-degree: 3%

---

# 关于 Adobe Experience Platform Data Connector {#about-aep-data-connector}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector现已弃用。 已弃用的功能仍然可用，但不会进一步增强或支持这些功能。 在此页面[中了解更多](../../rn/using/deprecated-features.md)

Adobe Experience Platform Data Connector通过将XTK数据（在Campaign中引入的数据）映射到Adobe Experience Platform上的Experience Data Model (XDM)数据，帮助现有客户使其数据在Adobe Experience Platform上可用。

请注意，该连接器是&#x200B;**单向**，将数据从Adobe Campaign Standard发送到Adobe Experience Platform。 数据永远不会从Adobe Experience Platform发送到Adobe Campaign Standard。

Adobe Experience Platform Data Connector面向&#x200B;**数据工程师**，他们了解Adobe Campaign Standard自定义资源，并了解客户的总数据架构应如何位于Adobe Experience Platform中。

以下部分介绍了在Campaign Standard和Adobe Experience Platform之间执行数据映射的关键步骤。 首先创建XDM架构和数据集。

![](assets/do-not-localize/how-to-video.png) [通过观看视频了解此功能](#video)

>[!NOTE]
>配置Adobe Experience Platform Data Connector并将数据成功摄取到Adobe Experience Platform中后，您需要启用数据集，以便将数据包含在实时客户资料中。
>
>可以通过API或Adobe Experience Platform界面执行此操作。 有关更多信息，请参阅专用文档：
>
>* [为实时客户个人资料启用数据集](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/datasets/dataset.html?lang=zh-Hans)
>* [使用API为Real-time Customer Profile和Identity服务配置数据集](https://experienceleague.adobe.com/docs/experience-platform/catalog/api/getting-started.html?lang=zh-Hans)

## 重要概念 {#key-concepts}

* 开箱即用映射仅适用于默认情况下Campaign Standard中提供的字段。 为了摄取所有自定义字段和资源，每个客户需要定义自己的映射。

* Adobe Experience Platform Data Connector将定期通过平台推送用户档案数据&#x200B;。 间隔持续时间为15分钟。 可以使用[Adobe Experience Platform API](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=zh-Hans)修改此值。

* 数据工程师可以发布、修改和暂停从Campaign到Adobe Experience Platform的映射。

* 可以映射任何定向维度。 建议为单个定向维度中的所有字段具有一个映射。

* 所有配置文件更新（包括渠道选择加入/选择退出）均包含在批量更新中。

* 任何Adobe Campaign Standard或XDM架构更改都需要手动重新映射&#x200B;。

* 跟踪日志和Broadlog数据会自动作为Experience事件摄取到Adobe Experience Platform。 此摄取过程实时流式传输到Adobe Experience Platform。

* Experience Cloud ID服务(ECID)是一个设备标识符，默认情况下通过Experience Events发送。

  它是分配给访客的唯一永久性ID，可供Platform Identity服务用来在不同的Experience Cloud解决方案中识别同一访客及其数据。 有关详细信息，请参阅[Experience Cloud Identity Service帮助](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hans)。

  >[!NOTE]
  >
  >请注意，如果两个或更多配置文件共享同一设备，则Unified Identity服务中这两个配置文件的ECID将相同。

## 限制 {#limitations}

* 不支持开箱即用的订阅事件传输。 要传输订阅事件，您可以在Adobe Experience Platform上创建相应的XDM和数据集，然后为这些数据配置自定义数据映射。

* 关于隐私请求（访问和删除操作），客户需要通过[隐私核心服务](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=zh-Hans#how-to-use-privacy-service-to-manage-privacy-job-requests)发出单独的请求：一个用于Campaign，一个用于Adobe Experience Platform。 有关此内容的更多信息，请参阅Campaign中的[关于隐私请求](https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=zh-Hans#getting-started)和[管理隐私请求](https://helpx.adobe.com/cn/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)。

* 对于每个XDM字段，需要在Adobe Experience Platform中完成DULE标签设置。 客户有责任应用DULE标签。

* 只有在Adobe Experience Platform中应用DULE标签后，对营销活动的限制才适用。 在此之前，所有数据都可用于所有类型的营销操作。

* 每15分钟运行一次批处理作业，它标识自最新批处理以来发生更改的记录。 如果所有记录在同一时间戳中更改，则可能会出现性能瓶颈，以管理所有配置文件的摄取

## 教程视频 {#video}

此视频概述Adobe Experience Platform Data Connector。

>[!VIDEO](https://video.tv.adobe.com/v/27304?quality=12&captions=eng)

[此处](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html?lang=zh-Hans)提供了与Adobe Experience Platform Data Connector相关的其他视频。
