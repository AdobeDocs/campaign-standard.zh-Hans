---
solution: Campaign Standard
product: campaign
title: 发送包含扩充字段的电子邮件
description: 下方的示例展示了如何使用通过加载文件活动，发送使用了（检索自外部文件的）附加数据的电子邮件。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileImport,main
feature: 工作流
role: 数据架构师
level: 中间
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 74%

---


# 发送包含扩充字段的电子邮件 {#sending-email-enriched-fields}

<!--A new example showing how to send an email containing additional data retrieved from a load file activity has been added. [Read more](example-2-email-with-enriched-fields)-->

利用加载文件活动，还可发送（在同一工作流使用外部文件）扩充了附加数据的电子邮件。

下方的示例展示了如何使用通过加载文件活动，发送使用了（检索自外部文件的）附加数据的电子邮件。在本例中，外部文件包含一系列用户档案及其关联的帐号。您想要导入此数据，以向每个用户档案发送一封包含其帐号的电子邮件。

![](assets/load_file_workflow_ex2.png)

要构建工作流，请执行以下步骤：

1. 将[查询](../../automating/using/query.md)活动拖放到工作流中，然后打开它以定义主目标。

   <!--The Query activity is presented in the [Query](../../automating/using/query.md) section.-->

1. 拖放[加载文件](../../automating/using/load-file.md)活动，将一些数据分配给用户档案。 在本例中，就是加载一个其中包含了对应于数据库某些用户档案之帐号的文件。

   ![](assets/load_file_activity.png)

1. 将[扩充](../../automating/using/enrichment.md)活动拖放到工作流中，并将加载文件和查询活动链接到工作流。

1. 在扩充活动的 **[!UICONTROL Advanced relations]** 选项卡中，选择 **[!UICONTROL 0 or 1 cardinality simple link]** 并定义要用于协调的字段。这里，我们使用“姓氏”将数据与数据库用户档案协调。

   ![](assets/load_file_enrichment_relation.png)

1. 在 **[!UICONTROL Additional data]** 选项卡中，选择要用在电子邮件中的元素。在此，选择帐号（通过加载文件活动检索之文件中的帐号列）。

   ![](assets/load_file_enrichment_select_element.png)

   <!--![](assets/load_file_enrichment_additional_data.png)-->

   有关更多信息，请参阅[扩充](../../automating/using/enrichment.md)一节。

1. 将[分段](../../automating/using/segmentation.md)活动拖放到您的工作流中，然后打开它以优化主目标。

   ![](assets/load_file_segmentation.png)

   有关更多信息，请参阅[分段](../../automating/using/segmentation.md)一节。

1. 将[电子邮件投放](../../automating/using/email-delivery.md)活动拖放到您的工作流中并打开它。

   <!--The Email delivery activity is presented in the [Email delivery](../../automating/using/email-delivery.md) section.-->

1. 添加个性化字段，并从 **[!UICONTROL Additional data (targetData)]** 节点选择扩充活动中定义的附加数据（此处为“帐号”）。这样即可动态检索电子邮件内容中每个用户档案的帐号。

   ![](assets/load_file_perso_field.png)

1. 保存电子邮件并启动工作流。

将发送电子邮件给目标。每个用户档案都会收到与其帐号相对应的电子邮件。

![](assets/load_file_email.png)
