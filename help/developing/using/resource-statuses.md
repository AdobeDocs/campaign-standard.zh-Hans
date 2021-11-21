---
title: 资源状态
description: 根据资源的发布状态发现不同的资源状态。
audience: developing
content-type: reference
topic-tags: about-custom-resources
feature: Data Model
role: Developer
level: Experienced
exl-id: 7290ebc5-8a58-4b7f-99bf-d942e37c944e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 1%

---

# 资源状态{#resource-statuses}

根据资源的发布或激活状态，资源可能具有不同的状态。

有两列专门用于在 **[!UICONTROL Custom resources]** 屏幕。

![](assets/schema_colonne_1.png)

**发布状态**

* **草稿**:资源刚刚创建或重新起草。 要创建数据库表以及相应的API，必须重新发布资源。 如果重新起草资源，则该资源在发布步骤后会自动变为不活动状态。
* **有待重新起草**:资源已重新起草。 重新起草过程将在下次发布期间进行。 重新起草是不可逆转的。 在重新起草和准备发布时，会显示多条警告消息以通知用户。

   有关重新起草的更多信息，请参阅 [删除资源](../../developing/using/deleting-a-resource.md).

   >[!NOTE]
   >
   >的 **[!UICONTROL Cancel re-draft]** 当要重新起草的资源仍包含通过其他资源的链接且其状态为“已发布”时，此选项将可用。 利用此选项可还原“重新起草”过程。 然后，自定义资源将返回到其原始状态。

* **已发布**:资源已发布。 如果资源在上次修改日期后进行了修改，则会显示一条消息，邀请您重新发布资源，以便考虑到最新修改。

的 **[!UICONTROL Do not publish latest modifications]** 字段会阻止在将来的发布期间考虑修改。

可以在自定义资源定义中配置此字段。
