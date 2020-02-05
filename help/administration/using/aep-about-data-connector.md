---
title: 关于Adobe Experience Platform Data Connector
description: 管理XDM架构，使您的Campaign Standard数据可在Adobe Experience platform上使用。
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
source-git-commit: 8ea3340e9ffb8b438c781aeff1a8554c9160474f

---


# 关于Adobe Experience Platform Data Connector {#about-aep-data-connector}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector目前处于测试阶段，可能会在不另行通知的情况下频繁进行更新。 客户必须托管在Azure上（目前仅针对北美）才能访问这些功能。 如果您希望访问，请联系Adobe客户关怀。

Adobe Experience Platform Data Connector将XTK数据（在Campaign中摄取的数据）映射到Adobe Experience Platform上的Experience Data Model(XDM)数据，从而帮助现有客户在Adobe Experience platform上提供数据。

请注意，该连接器是 **单向的** ，并将数据从Adobe Campaign Standard发送到Adobe Experience Platform。 数据从不从Adobe Experience platform发送到Adobe Campaign Standard。

Adobe Experience Platform Data Connector适用于了解Adobe Campaign Standard自定义资源并了解客户的整体数据架构如何位于Adobe Experience platform内的数据工程师。 ****

以下各节介绍了在Campaign standard和Adobe Experience platform之间执行数据映射的关键步骤。 这从创建XDM架构和数据集开始。

此页中还提供操作说 [明视频](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html)。

>[!NOTE]
>配置Adobe Experience Platform Data Connector并成功将数据引入Adobe Experience Platform后，您需要启用数据集，以便将数据包含在实时客户档案中。
>
>这可以通过API或Adobe Experience Platform界面执行。 有关详细信息，请参阅专用文档：
>
>* [为实时客户配置文件启用数据集](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/data_ingestion_tutorial/data_ingestion_tutorial.md)
>* [使用API为实时客户配置文件和标识服务配置数据集](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/unified_profile_dataset_tutorial/unified_profile_dataset_api_tutorial.md)


## 重要概念 {#key-concepts}

* 开箱即用映射仅适用于默认情况下在Campaign standard中提供的字段。 要获取所有自定义字段和资源，每个客户都需要定义自己的映射。

* Adobe Experience Platform Data Connector将定期在平台中推送配置文件数据&#x200B;。间隔时间为15mn。 此值不可修改。

   >[!NOTE]
   >
   >此持续时间可以使用 [Adobe Experience Platform API进行修改](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/authenticate_to_acp_tutorial/authenticate_to_acp_tutorial.md)。

* 数据工程师可以发布、修改和暂停从Campaign到Adobe Experience Platform的映射。

* 可以映射任何定位维度。 建议为单个定位维中的所有字段有一个单一映射。

* 所有配置文件更新（包括渠道选择加入／选择退出）都是批量更新的一部分。

* 需要手动重新映射任何Adobe Campaign Standard或XDM架构更&#x200B;改。

* 跟踪日志和Broadlog数据会作为体验事件自动摄取到Adobe Experience Platform。 该摄取将实时流化到Adobe Experience Platform。

## 限制 {#limitations}

* 不支持现成的订阅事件传输。 要传输订阅事件，您可以在Adobe Experience Platform上创建相应的XDM和数据集，然后为这些数据配置自定义数据映射。

* 关于隐私请求，客户需要分别提出Campaign核心隐私服务和Adobe Experience Platform的请求，以便执行访问和删除操作。

* 对于每个XDM字段，需要在Adobe Experience platform中进行DULE标签。 这是应用DULE标签的客户责任。

* 只有在Adobe Experience platform中应用DULE标签后，营销操作限制才可用。 在此之前，所有数据都可用于所有类型的营销操作。

* 每15分钟，批处理作业就会运行一次，它会识别自最新批处理以来已更改的记录。 如果所有记录在同一时间戳发生更改，则可能出现性能瓶颈以管理所有配置文件的摄取
