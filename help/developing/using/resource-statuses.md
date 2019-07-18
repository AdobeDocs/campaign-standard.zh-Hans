---
title: 资源状态
seo-title: 资源状态
description: 资源状态
seo-description: 根据其发布状态发现不同的资源状态。
page-status-flag: 从未激活
uuid: 215c0a2e-27ec-43f3-baac-1eaac7640784
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: 关于自定义资源
discoiquuid: 85516477-1b95-4273-a0 a7-d2 cbb9950 afd
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Resource statuses{#resource-statuses}

资源可以根据其发布或激活状态具有不同的状态。

There are two columns dedicated to displaying these statuses in the **[!UICONTROL Custom resources]** screen.

![](assets/schema_colonne_1.png)

**出版物状态**

* **草稿**：资源刚刚创建或重新起草。要创建数据库表以及相应的API，必须重新发布资源。如果资源正在重新起草，则在发布步骤之后会自动呈现不活动。
* **正在等待重新起草**：资源已重新起草。重新起草过程将在下一个出版物中进行。重新制图是不可逆转的。在重新起草时，有几条警告消息会提醒用户这一事实，然后准备发布。

   For more on re-drafting, see [Deleting a resource](../../developing/using/deleting-a-resource.md).

   >[!NOTE]
   >
   >The **[!UICONTROL Cancel re-draft]** option is available when the resource that you want to re-draft still contains links through other resources with the "Published" status. 此选项允许您还原“重新起草”流程。自定义资源随后将恢复其初始状态。

* **已发布**：资源已发布。如果在上次修改日期之后修改资源，则会显示一条消息，要求用户重新发布，以便考虑最新修改。

**[!UICONTROL Do not publish latest modifications]** 此字段可防止在将来的出版物中考虑修改内容。

此字段可在自定义资源定义中进行配置。
