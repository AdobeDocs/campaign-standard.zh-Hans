---
title: Integrated Customer Profile
description: 在单个视图中跟踪每次客户互动：在整个客户生命周期中都会更新Adobe Campaign整合的客户用户档案。
audience: audiences
content-type: reference
topic-tags: managing-profiles
context-tags: marketingHistory,main
feature: Profiles
role: User
level: Beginner
exl-id: cf3c6408-7fa0-423a-b34b-f4fee771fb47
TQID: https://experienceleague.adobe.com/a-v47cX0DxN6dzLQs-r4e2yMajLD6GHIVXXEX9Ol-lY
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: b12f6872-9271-4369-85e5-86969a0b99a2
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 282
ht-degree: 41%

---

# Integrated Customer Profile{#integrated-customer-profile}

可以为您数据库中的每个联系人提供整合的客户轮廓。 此营销历史可将与客户联系有关的所有相关营销信息，合并到一个视图中。 然后，您即可在一个中心位置访问所有数字行为、线上和线下交易：联系信息、收到的电子邮件、跟踪日志、订阅和退订等。

要访问整合的客户轮廓，请执行以下步骤：

1. 从Adobe Campaign主页中，单击&#x200B;**[!UICONTROL Customer profiles]**&#x200B;卡或&#x200B;**配置文件**&#x200B;选项卡以显示配置文件列表。

1. 要根据特定字段搜索配置文件，请打开搜索窗格，然后选择要执行搜索的字段。


   ![](assets/profile-search.png)

1. 指定要搜索的值，然后按Enter。

   >[!NOTE]
   >
   >请注意，可以根据电子邮件、名字和姓氏字段以及在扩展资源时添加的自定义字段执行搜索。
   >
   >搜索区分大小写，并且只对前缀执行。 例如，您将无法使用用户档案的姓氏查找用户档案。

1. 选择联系人以打开其用户档案。

   ![](assets/mkt_hist_access.png)

然后，您可以访问此联系人的&#x200B;**营销历史**。

本页会收集关于轮廓的重要信息以及事件列表。

单击列表中的事件以将其打开：您可以访问已发送的消息或用户档案已订阅的服务。

![](assets/mkt_hist_view.png)

>[!NOTE]
>
>营销历史也可使用 Adobe Campaign Standard API 访问。 有关更多信息，请参阅[专用文档](../../api/using/interacting-with-marketing-history.md)。
