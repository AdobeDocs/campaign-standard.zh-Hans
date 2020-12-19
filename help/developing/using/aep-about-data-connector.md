---
solution: Campaign Standard
product: campaign
title: 关于 Adobe Experience Platform Data Connector
description: 管理XDM模式，使您的Campaign Standard数据在Adobe Experience Platform可用。
audience: administration
content-type: reference
topic-tags: configuring-channels
translation-type: tm+mt
source-git-commit: 2a92600df01fd3c78a2b35c8034a2ce347e5c1d8
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 5%

---


# 关于 Adobe Experience Platform Data Connector {#about-aep-data-connector}

>[!IMPORTANT]
>
>Adobe Experience Platform数据连接器目前处于测试阶段，可能会在不通知的情况下频繁进行更新。 客户必须托管在Azure上（目前仅限北美的beta版），才能访问这些功能。 如果您想要访问，请联系Adobe客户服务中心。

Adobe Experience Platform数据连接器通过将XTK数据(以活动摄取的数据)映射到Adobe Experience Platform的体验数据模型(XDM)数据，帮助现有客户在Adobe Experience Platform提供数据。

请注意，连接器为&#x200B;**单向**&#x200B;并将数据从Adobe Campaign Standard发送到Adobe Experience Platform。 数据从不从Adobe Experience Platform发送到Adobe Campaign Standard。

Adobe Experience Platform数据连接器面向&#x200B;**数据工程师**，他们了解Adobe Campaign Standard定制资源并了解客户的整体数据模式在Adobe Experience Platform内部应如何。

以下各节介绍在Campaign Standard和Adobe Experience Platform之间执行数据映射的关键步骤。 此开始与创建XDM模式和数据集相关。

![](assets/do-not-localize/how-to-video.png) [在视频中发现此功能](#video)

>[!NOTE]
>配置Adobe Experience Platform数据连接器并成功将数据引入Adobe Experience Platform后，您需要启用数据集，以便将数据包含在实时客户用户档案中。
>
>这可以通过API或Adobe Experience Platform接口执行。 有关详细信息，请参阅专用文档：
>
>* [为实时客户用户档案启用数据集](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/datasets/dataset.html)
>* [使用API为实时客户用户档案和身份服务配置数据集](https://docs.adobe.com/content/help/en/experience-platform/catalog/api/getting-started.html)


## 重要概念 {#key-concepts}

* 现成映射仅适用于默认以Campaign Standard提供的字段。 要获取所有自定义字段和资源，每个客户都需要定义自己的映射。

* Adobe Experience Platform数据连接器将定期推送用户档案数据通过平&#x200B;台。 时间间隔为15mn。 可以使用[Adobe Experience PlatformAPI](https://docs.adobe.com/content/help/en/experience-platform/ingestion/home.html)修改此值。

* 数据工程师可以发布、修改和暂停从活动到Adobe Experience Platform的映射。

* 可以映射任何定位维度。 建议在一个定位维度中对所有字段进行一个映射。

* 所有用户档案更新(包括渠道加入／退出)都是批更新的一部分。

* 任何Adobe Campaign Standard或XDM模式更改都需要手动重新映射&#x200B;。

* 跟踪日志和Broadlog数据作为体验事件自动摄取到Adobe Experience Platform。 这个摄取流实时传输到Adobe Experience Platform。

* Experience CloudID服务(ECID)是默认使用体验事件发送的设备标识符。

   它是分配给访客的唯一永久ID，平台标识服务可以使用它来识别不同访客解决方案中的相同Experience Cloud及其数据。 有关详细信息，请参阅[Experience Cloud身份服务帮助](https://docs.adobe.com/content/help/en/id-service/using/home.html)。

   >[!NOTE]
   >
   >请注意，如果两个或多个用户档案共享同一设备，则统一标识服务中这两个用户档案的ECID将相同。

## 限制{#limitations}

* 不支持订阅事件的现成传输。 要传输订阅事件，您可以在Adobe Experience Platform创建相应的XDM和数据集，然后为这些数据配置自定义数据映射。

* 关于隐私请求（访问和删除操作），客户需要通过[隐私核心服务](https://docs.adobe.com/content/help/en/experience-platform/privacy/home.html#how-to-use-privacy-service-to-manage-privacy-job-requests)发送单独的请求：一个是活动，一个是Adobe Experience Platform。 有关详细信息，请参阅活动中的[关于隐私请求](https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=zh-Hans#getting-started)和[管理隐私请求](https://helpx.adobe.com/cn/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)。

* 对于每个XDM字段，需要在Adobe Experience Platform进行DULE标记。 这是应用DULE标签的客户责任。

* 只有在Adobe Experience Platform应用DULE标签后，市场营销操作限制才可用。 在此之前，所有数据均可用于所有类型的营销操作。

* 每15分钟，批处理作业就会运行，它会标识自最新批处理后更改的记录。 如果所有记录在同一时间戳发生更改，则可能出现性能瓶颈以管理所有用户档案的摄取

## 教程视频{#video}

此视频概述了Adobe Experience Platform数据连接器。

https://video.tv.adobe.com/v/27304?quality=12&amp;captions=chi_hans

有关“Adobe Experience Platform数据连接器”的其他视频，请访问[此处](https://docs.adobe.com/content/help/zh-Hans/campaign-standard-learn/tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.translate.html)。
