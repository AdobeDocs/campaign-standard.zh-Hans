---
title: 资源状态
description: 根据其发布状态发现不同的资源状态。
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

根据其发布或激活状态，资源可以具有不同的状态。

有两个列专门用于在&#x200B;**[!UICONTROL Custom resources]**&#x200B;屏幕中显示这些状态。

![](assets/schema_colonne_1.png)

**发布状态**

* **草稿**：刚刚创建或重新起草了资源。 要创建数据库表和相应的API，必须重新发布资源。 如果重新起草资源，则在发布步骤后该资源会自动失效。
* **正在等待重新起草**：资源已重新起草。 重新草稿过程将在下次发布时进行。 重新起草是不可逆转的。 在重新起草和准备发布时，显示多个警告消息以通知用户。

  有关重新起草的详细信息，请参阅[删除资源](../../developing/using/deleting-a-resource.md)。

  >[!NOTE]
  >
  >当要重新草稿的资源仍然包含通过其他资源发送的处于“已发布”状态的链接时，**[!UICONTROL Cancel re-draft]**&#x200B;选项可用。 此选项允许您恢复“重新起草”流程。 然后，自定义资源将返回到其原始状态。

* **已发布**：资源已发布。 如果资源在最后一次修改日期之后被修改，则会显示一条消息，邀请您重新发布该资源，以便考虑最新的修改。

**[!UICONTROL Do not publish latest modifications]**&#x200B;字段阻止在将来的发布期间考虑修改。

可在自定义资源定义中配置此字段。
