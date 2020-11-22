---
solution: Campaign Standard
product: campaign
title: 资源状态
description: 根据不同的资源发布状态发现不同的资源状态。
audience: developing
content-type: reference
topic-tags: about-custom-resources
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 1%

---


# 资源状态{#resource-statuses}

根据资源的发布或激活状态，资源可以具有不同的状态。

有两列专门用于在屏幕中显示这些 **[!UICONTROL Custom resources]** 状态。

![](assets/schema_colonne_1.png)

**发布状态**

* **草稿**:资源刚刚创建或重新起草。 要创建数据库表和相应的API，必须重新发布资源。 如果正在重新起草资源，则在发布步骤后，该资源将自动变为非活动状态。
* **待重新起草**:资源重新起草。 重新起草过程将在下一次发布期间进行。 重新起草是不可逆转的。 在重新起草和准备发布时，会显示多条警告消息以通知用户。

   有关重新起草的详细信息，请参 [阅删除资源](../../developing/using/deleting-a-resource.md)。

   >[!NOTE]
   >
   >当您 **[!UICONTROL Cancel re-draft]** 要重新起草的资源仍包含通过其他资源的链接并且其状态为“已发布”时，此选项可用。 此选项允许您还原“重新起草”过程。 自定义资源随后将恢复其原始状态。

* **已发布**:资源已发布。 如果资源在上次修改日期后被修改，则会显示一条消息，要求您重新发布资源，以便考虑最新修改。

该字 **[!UICONTROL Do not publish latest modifications]** 段可防止在将来的发布过程中考虑修改。

可以在自定义资源定义中配置此字段。
