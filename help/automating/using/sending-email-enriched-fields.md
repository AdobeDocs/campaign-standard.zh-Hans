---
title: 发送包含丰富字段的电子邮件
description: 以下示例演示如何使用通过加载文件活动从外部文件检索到的其他数据来发送电子邮件。
page-status-flag: never-activated
uuid: 69af12cc-6f82-4977-9f53-aa7bc26f5d7e
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 584ff893-9b1b-46c9-9628-714ab349ab88
context-tags: fileImport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 0%

---


# 发送包含丰富字段的电子邮件 {#sending-email-enriched-fields}

<!--A new example showing how to send an email containing additional data retrieved from a load file activity has been added. [Read more](example-2-email-with-enriched-fields)-->

加载文件活动还允许在同一工作流中从外部文件发送包含附加数据的电子邮件。

以下示例演示如何使用通过加载文件活动从外部文件检索到的其他数据来发送电子邮件。 在此示例中，外部文件包含一列表用户档案及其关联的帐号。 您要导入此数据，以向每个用户档案发送一封包含其帐号的电子邮件。

![](assets/load_file_workflow_ex2.png)

要构建工作流，请按照以下步骤操作：

1. 将查询 [活动拖](../../automating/using/query.md) 放到您的工作流中，然后打开它以定义主目标。

   <!--The Query activity is presented in the [Query](../../automating/using/query.md) section.-->

1. 拖放“加载 [文件](../../automating/using/load-file.md) ”活动，将一些数据分配给用户档案。 在此示例中，加载一个包含与某些用户档案库对应的帐号的文件。

   ![](assets/load_file_activity.png)

1. 将扩充 [活动拖](../../automating/using/enrichment.md) 放到您的工作流中，并将加载文件和查询活动链接到该工作流。

1. 在扩充 **[!UICONTROL Advanced relations]** 活动的选项卡中，选择 **[!UICONTROL 0 or 1 cardinality simple link]** 要用于对帐的字段并定义这些字段。 这里，我们使用姓氏将数据与数据库用户档案协调起来。

   ![](assets/load_file_enrichment_relation.png)

1. 在选 **[!UICONTROL Additional data]** 项卡中，选择要在电子邮件中使用的元素。 在此选择帐户号(从您通过加载文件活动检索的文件中的列)。

   ![](assets/load_file_enrichment_select_element.png)

   <!--![](assets/load_file_enrichment_additional_data.png)-->

   有关此内容的详细信息，请参 [阅扩充](../../automating/using/enrichment.md) 部分。

1. 将分段活动拖 [放到](../../automating/using/segmentation.md) 您的工作流中，然后打开它以细化主目标。

   ![](assets/load_file_segmentation.png)

   有关此方面的详细信息，请参 [阅分段](../../automating/using/segmentation.md) 部分。

1. 将电子邮件投放 [活动拖](../../automating/using/email-delivery.md) 放到您的工作流中，然后将其打开。

   <!--The Email delivery activity is presented in the [Email delivery](../../automating/using/email-delivery.md) section.-->

1. 添加个性化字段，并从节点选择扩充活动（此处为帐户号）中定义的其他 **[!UICONTROL Additional data (targetData)]** 数据。 这允许动态检索电子邮件内容中每个用户档案的帐号。

   ![](assets/load_file_perso_field.png)

1. 保存电子邮件并开始工作流。

电子邮件将发送给目标。 每个用户档案都会收到包含其相应帐号的电子邮件。

![](assets/load_file_email.png)
