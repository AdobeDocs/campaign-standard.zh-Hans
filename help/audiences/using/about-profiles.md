---
solution: Campaign Standard
product: campaign
title: 关于用户档案
description: 联系人作为用户档案存储在 Campaign 数据库中，并在其整个生命周期内不断更新。
audience: audiences
content-type: reference
topic-tags: managing-profiles
context-tags: recipient,overview
feature: 用户档案
role: User
level: Beginner
exl-id: 65310e00-567f-4fae-89bc-b1d5591fca77
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 100%

---

# 关于用户档案{#about-profiles}

您可以使用 Adobe Campaign 在联系人的整个生命周期内对其进行管理：创建、导入、定位、操作跟踪、更新等。联系人作为包含相关链接信息的用户档案存储在数据库中：姓氏、名字、地址、订阅、投放等。

>[!NOTE]
>
>Adobe Campaign Standard API 也可以使用用户档案。有关更多信息，请参阅[专用文档](../../api/using/retrieving-profiles.md)。

![](assets/marketing_history.png)

创建营销策划时，您可以根据简单或高级条件选择用户档案，从而定义投放的目标。从技术上讲，用户档案是数据库中的一个条目，其中包含定向、鉴别和跟踪行为所需的全部信息。

用户档案可以是：客户、潜在客户、订阅新闻通讯的个人、收件人、用户或任何其他对象，具体取决于您的组织。要定义各种类型的用户档案，请使用[定向维度](../../automating/using/query.md#targeting-dimensions-and-resources)。
