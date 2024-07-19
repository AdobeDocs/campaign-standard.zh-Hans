---
title: 协调
description: 利用协调活动，可将未识别的数据链接到现有资源。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: reconciliation,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: ed2e3793-6164-48af-9043-42dc43fa8ed4
source-git-commit: c2c8d2d05bbc376e2153448ca0a9e6ba0f367420
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 78%

---

# 协调{#reconciliation}

## 说明 {#description}

![](assets/reconciliation.png)

利用 **[!UICONTROL Reconciliation]** 活动，可将未识别的数据链接到现有资源。

## 使用环境 {#context-of-use}

**[!UICONTROL Reconciliation]** 活动主要用于数据管理目的，并包含两种不同的使用情形：

* 添加关系：使用 **[!UICONTROL Links]** 选项卡可在集客数据和多个其他 Adobe Campaign 数据库维度之间添加链接。

  例如，包含购买数据的文件也可能包含用于识别所购买产品以及买方的信息。因此，文件数据会涉及额外的两个维度（除&#x200B;**购买**&#x200B;维度外）：**产品**&#x200B;和&#x200B;**用户档案**。然后，需要创建这些维度与&#x200B;**“购买”**&#x200B;维度之间的关系（请参阅以下示例）。

  定义关系时，将向集客数据添加列，以引用链接维度的外键。

  >[!NOTE]
  >
  >此操作意味着链接维度的数据已在数据库中。例如，如果导入一个购买文件，其中显示了购买哪个产品、购买时间、购买客户等，则数据库中必然已经存在该产品和客户。

* 数据标识：使用 **[!UICONTROL Identification]** 选项卡，您只需将集客数据链接到 Adobe Campaign 数据库中现有维度的列即可。活动完成后，该数据会被标识为属于已定义的维度。

  例如，您随后可以执行保存受众、数据库更新等操作。

例如，**[!UICONTROL Reconciliation]**&#x200B;活动可以放置在加载数据活动之后，以将非标准数据导入数据库。

虽然&#x200B;**扩充**&#x200B;活动允许您定义要在工作流中处理的附加数据（使用&#x200B;**扩充**&#x200B;活动组合来自多个集的数据，或创建指向临时资源的链接），但&#x200B;**协调**&#x200B;活动允许您将未识别的数据链接到现有资源。 协调操作意味着链接维度的数据已在数据库中。 [此部分](#use-cases-reconciliation)中有用例可用。


## 配置 {#configuration}

1. 将 **[!UICONTROL Reconciliation]** 活动拖放到您的工作流中的一个过渡（该过渡包含定向维度并非直接来自 Adobe Campaign 的群体）后方。有关更多信息，请参阅[定向维度和资源](../../automating/using/query.md#targeting-dimensions-and-resources)。
1. 选择活动，然后使用所显示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按钮将其打开。
1. 如果要定义集客数据与其他数据库维度之间的链接，请转到 **[!UICONTROL Links]** 选项卡。

   根据需要，添加相应数量的关系。对于每个关系，首先选择链接的维度，然后在链接详细信息中指定相应的字段。

1. 如果您只想识别集客数据，请转到 **[!UICONTROL Identification]** 选项卡并勾选 **[!UICONTROL Identify the document from the working data]** 方框。

   选择要协调集客数据的定向维度。

   添加协调条件，以将集客过渡记录链接到选定的定向维度记录。如果指定了多个标准，则必须对所有标准进行验证，以确保所有数据之间的链接正常工作。

   选择 **[!UICONTROL Processing unidentified source lines]** 模式：

   * **[!UICONTROL Ignore them]**：仅在活动的叫客过渡中保留可识别数据。
   * **[!UICONTROL Keep in the outbound population]**：在活动的叫客过渡中保留来自集客过渡的所有数据。

1. 确认活动的配置并保存工作流。


## 用例{#use-cases-reconciliation}

了解如何在以下用例中使用此活动：

* [用例：使用关系进行数据协调](../../automating/using/reconciliation-using-relations.md)
* [用例：使用协调进行数据更新](../../automating/using/data-update-reconciliation.md)
* [用例：使用数据库协调文件受众](../../automating/using/reconcile-file-audience-with-database.md)