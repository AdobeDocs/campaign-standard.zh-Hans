---
title: 发送包含扩充字段的电子邮件
description: 下方的示例展示了如何使用通过加载文件活动，发送使用了（检索自外部文件的）附加数据的电子邮件。
page-status-flag: never-activated
uuid: 69af12cc-6f82-4977-9f53-aa7bc26f5d7e
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 584ff893-9b1b-46c9-9628-714ab349ab88
context-tags: fileImport,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 发送包含扩充字段的电子邮件 {#sending-email-enriched-fields}

<!--A new example showing how to send an email containing additional data retrieved from a load file activity has been added. [Read more](example-2-email-with-enriched-fields)-->

利用加载文件活动，还可发送（在同一工作流使用外部文件）扩充了附加数据的电子邮件。

下方的示例展示了如何使用通过加载文件活动，发送使用了（检索自外部文件的）附加数据的电子邮件。在本例中，外部文件包含一系列用户档案及其关联的帐号。您想要导入此数据，以向每个用户档案发送一封包含其帐号的电子邮件。

![](assets/load_file_workflow_ex2.png)

要构建工作流，请按照以下步骤操作：

1. Drag and drop a [Query](../../automating/using/query.md) activity into your workflow and open it to define the main target.

   <!--The Query activity is presented in the [Query](../../automating/using/query.md) section.-->

1. Drag and drop a [Load file](../../automating/using/load-file.md) activity to assign some data to a profile. 在本例中，就是加载一个其中包含了对应于数据库某些用户档案之帐号的文件。

   ![](assets/load_file_activity.png)

1. Drag and drop an [Enrichment](../../automating/using/enrichment.md) activity into your workflow and link the load file and query activities to it.

1. 在扩充活动的 **[!UICONTROL Advanced relations]** 选项卡中，选择 **[!UICONTROL 0 or 1 cardinality simple link]** 并定义要用于协调的字段。这里，我们使用“姓氏”将数据与数据库用户档案协调。

   ![](assets/load_file_enrichment_relation.png)

1. 在 **[!UICONTROL Additional data]** 选项卡中，选择要用在电子邮件中的元素。在此，选择帐号（通过加载文件活动检索之文件中的帐号列）。

   ![](assets/load_file_enrichment_select_element.png)

   <!--![](assets/load_file_enrichment_additional_data.png)-->

   有关更多信息，请参阅[扩充](../../automating/using/enrichment.md)一节。

1. Drag and drop a [Segmentation](../../automating/using/segmentation.md) activity into your workflow and open it to refine the main target.

   ![](assets/load_file_segmentation.png)

   有关更多信息，请参阅[分段](../../automating/using/segmentation.md)一节。

1. Drag and drop an [Email delivery](../../automating/using/email-delivery.md) activity into your workflow and open it.

   <!--The Email delivery activity is presented in the [Email delivery](../../automating/using/email-delivery.md) section.-->

1. 添加个性化字段，并从 **[!UICONTROL Additional data (targetData)]** 节点选择扩充活动中定义的附加数据（此处为“帐号”）。这样即可动态检索电子邮件内容中每个用户档案的帐号。

   ![](assets/load_file_perso_field.png)

1. 保存电子邮件并启动工作流。

将发送电子邮件给目标。每个用户档案都会收到与其帐号相对应的电子邮件。

![](assets/load_file_email.png)
