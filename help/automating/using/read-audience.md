---
title: 读取受众
description: 阅读受众活动允许您检索现有受众，并通过应用其他过滤条件来优化它。
page-status-flag: never-activated
uuid: 58c54e71-f4a7-4ae9-80a3-33c379ab1db9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 674684e5-8830-4d2f-ba97-59ed4ba7422f
context-tags: readAudience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 1%

---


# 读取受众{#read-audience}

## 说明 {#description}

![](assets/prefill.png)

该 **[!UICONTROL Read audience]** 活动允许您检索现有受众，并通过应用其他过滤条件来优化它。

## 使用环境 {#context-of-use}

活动 **[!UICONTROL Read audience]** 是活动的一个更简单的版本， **[!UICONTROL Query]** 专为只需要选择现有受众的情况而设计。

**相关主题**

* [用例： 合并两家精炼受众](../../automating/using/union-on-two-refined-audiences.md)
* [用例： 协调文件受众与数据库](../../automating/using/reconcile-file-audience-with-database.md)

## Configuration {#configuration}

1. 将活动放 **[!UICONTROL Read audience]** 入您的工作流中。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮打开它。
1. 从选项卡中选择要检索的 **[!UICONTROL Properties]** 受众。

   您可以检索以下受众类型： **[!UICONTROL List]**、 **[!UICONTROL Query]**&#x200B;和 **[!UICONTROL File]****[!UICONTROL Experience Cloud]**。 有关受众类型的详细信息，请参阅 [受众文档](../../audiences/using/about-audiences.md) 。

   通过 **[!UICONTROL Use a dynamic audience]** 此选项，您可以根据工作流的受众变量定义目标的事件名称。 有关此内容的详细信息，请参阅使 [用活动变量自定义事件](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) 一节。

   ![](assets/readaudience_activity1.png)

1. 如果要对所选受众应用其他过滤，请通过该活动的选 **[!UICONTROL Source filtering]** 项卡添加条件。

   有关创建筛选条件的详细信息，请参阅创 [建查询文](../../automating/using/editing-queries.md#creating-queries) 档。

1. 确认活动的配置并保存工作流。
