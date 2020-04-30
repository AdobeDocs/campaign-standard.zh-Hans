---
title: 关于 Adobe Experience Platform Data Connector
description: 管理XDM模式，使您的Campaign Standard数据可在Adobe Experience Platform上使用。
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9388df151eabbc6f63461e854d0276c14d9ef93d

---


# 关于 Adobe Experience Platform Data Connector {#about-aep-data-connector}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector目前处于测试阶段，可能会在不另行通知的情况下频繁进行更新。 客户必须托管在Azure上（目前仅针对北美）才能访问这些功能。 如果您希望访问，请联系Adobe客户关怀。

Adobe Experience Platform Data Connector将XTK数据(以活动摄取的数据)映射到Adobe Experience Platform上的Experience Data Model(XDM)数据，从而帮助现有客户在Adobe Experience Platform上提供数据。

请注意，该连接器是 **单向的** ，并将数据从Adobe Standard发送到Adobe Experience Platform。 数据从不从Adobe Experience Platform发送到Adobe Campaign标准版。

Adobe Experience Platform Data Connector适用于理解 **** Adobe Campaign标准自定义资源并了解客户的整体数据模式如何存在于Adobe Experience Platform中的数据工程师。

以下各节介绍了在Campaign Standard与Adobe Experience Platform之间执行数据映射的关键步骤。 这与创建XDM模式和数据集相开始。

此页中还提供操作说 [明视频](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html)。

>[!NOTE]
>配置Adobe Experience Platform Data Connector并成功将数据引入Adobe Experience Platform后，您需要启用数据集，以便将数据包含在实时客户用户档案中。
>
>这可以通过API或Adobe Experience Platform界面执行。 有关详细信息，请参阅专用文档：
>
>* [为实时客户用户档案启用数据集](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/datasets/dataset.html)
>* [使用API为实时客户用户档案和标识服务配置数据集](https://docs.adobe.com/content/help/en/experience-platform/catalog/api/getting-started.html)


## 重要概念 {#key-concepts}

* “开箱即用”映射仅适用于默认情况下以Campaign Standard形式提供的字段。 要获取所有自定义字段和资源，每个客户都需要定义自己的映射。

* Adobe Experience Platform Data Connector将定期推送用户档案数据通过平台&#x200B;。间隔时间为15mn。 此值可以使用 [Adobe Experience Platform API进行修改](https://docs.adobe.com/content/help/en/experience-platform/ingestion/home.html)。

* 数据工程师可以发布、修改和暂停从活动到Adobe Experience Platform的映射。

* 可以映射任何定位维度。 建议在单个定位维度中为所有字段建立一个映射。

* 所有用户档案更新(包括渠道选择加入／选择退出)都是批更新的一部分。

* 任何Adobe Campaign标准或XDM模式更改都需要手动重新映射&#x200B;。

* 跟踪日志和Broadlog数据作为体验事件自动摄取到Adobe Experience Platform。 此摄取内容会实时流化到Adobe Experience Platform。

* Experience Cloud ID Service(ECID)是默认情况下随Experience事件发送的设备标识符。

   它是分配给访客的唯一永久ID，平台标识服务可以使用它识别不同Experience Cloud解决方案中的同一访客及其数据。 有关详细信息，请参阅 [Experience Cloud Identity Service帮助](https://docs.adobe.com/content/help/en/id-service/using/home.html)。

   >[!NOTE]
   >
   >请注意，如果两个或两个以上用户档案共享同一设备，则统一标识服务中这两个用户档案的ECID将相同。

## 限制 {#limitations}

* 不支持现成的订阅事件传输。 要传输订阅事件，您可以在Adobe Experience Platform上创建相应的XDM和数据集，然后为这些数据配置自定义数据映射。

* 关于隐私请求（访问和删除操作），客户需要单独提出请求：一个用于通过隐私核心服务集成进行活动(请参 [阅本节](https://helpx.adobe.com/campaign/kb/acs-privacy.html#righttoaccess))，另一个用于通过其隐私服务进行Adobe Experience Platform [的集成](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ccpa)。 有关访问和删除请求的详细信息，请参 [阅此页](https://helpx.adobe.com/campaign/kb/acs-privacy.html#righttoaccess)。

* 对于每个XDM字段，需要在Adobe Experience Platform中进行DULE标签。 这是应用DULE标签的客户责任。

* 只有在Adobe Experience Platform中应用DULE标签后，营销操作限制才可用。 在此之前，所有数据都可用于所有类型的营销操作。

* 每15分钟，批处理作业就会运行一次，它会识别自最新批处理以来已更改的记录。 如果所有记录在同一时间戳发生更改，则可能出现性能瓶颈以管理所有用户档案的摄取
