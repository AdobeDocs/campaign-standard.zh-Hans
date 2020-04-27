---
title: 资源状态
description: 根据不同的资源状态发现其发布状态。
page-status-flag: never-activated
uuid: 215c0a2e-27ec-43f3-baac-1eaac7640784
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: about-custom-resources
discoiquuid: 85516477-1b95-4273-a0a7-d2cbb9950afd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8852adb5edeb42eba1acf2911c988071104f1401

---


# 资源状态{#resource-statuses}

根据资源的发布或激活状态，资源可以具有不同的状态。

有两列专用于在屏幕中显示这些状 **[!UICONTROL Custom resources]** 态。

![](assets/schema_colonne_1.png)

**发布状态**

* **草稿**:资源刚刚创建或重新起草。 要创建数据库表和相应的API，必须重新发布资源。 如果正在重新起草资源，则在发布步骤后，该资源会自动变为非活动状态。
* **待重新起草**:资源重新起草。 重新起草过程将在下一次发布期间进行。 重新起草是不可逆转的。 在重新起草和准备发布时，会显示若干警告消息以通知用户。

   有关重新起草的详细信息，请参 [阅删除资源](../../developing/using/deleting-a-resource.md)。

   >[!NOTE]
   >
   >当您 **[!UICONTROL Cancel re-draft]** 要重新草拟的资源仍包含通过其他资源的链接并且其状态为“已发布”时，此选项才可用。 此选项允许您还原“重新起草”过程。 然后，自定义资源将返回其原始状态。

* **已发布**:资源已发布。 如果资源在上次修改日期后被修改，则会显示一条消息，要求您重新发布资源，以便考虑到最新修改。

该字 **[!UICONTROL Do not publish latest modifications]** 段可防止在将来的发布过程中考虑修改。

可以在自定义资源定义中配置此字段。
