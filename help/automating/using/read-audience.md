---
title: 读取受众
description: 利用读取受众活动，可检索现有受众，并通过应用附加筛选条件来优化现有受众。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 9a77a2c7-cc1c-416f-8103-bb7d5c84a373
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 87%

---

# 读取受众{#read-audience}

## 说明 {#description}

![](assets/prefill.png)

利用 **[!UICONTROL Read audience]** 活动，可检索现有受众，并通过应用附加筛选条件来优化现有受众。

## 使用环境 {#context-of-use}

**[!UICONTROL Read audience]** 活动是 **[!UICONTROL Query]** 活动的简化版本，专为只需要选择现有受众的情况而设计。

**相关主题**

* [用例：两个优化受众的并集](../../automating/using/union-on-two-refined-audiences.md)
* [用例：使用数据库协调文件受众](../../automating/using/reconcile-file-audience-with-database.md)

## 配置 {#configuration}

1. 将 **[!UICONTROL Read audience]** 活动拖放到工作流中。
1. 选择活动，然后使用所显示快捷操作中的 ![](assets/edit_darkgrey-24px.png) 按钮将其打开。
1. 从 **[!UICONTROL Properties]** 选项卡中选择要检索的受众。

   您可以检索以下受众类型：**[!UICONTROL List]**、**[!UICONTROL Query]**、**[!UICONTROL File]** 和 **[!UICONTROL Experience Cloud]**。有关受众类型的更多信息，请参阅[受众](../../audiences/using/about-audiences.md)文档。

   利用 **[!UICONTROL Use a dynamic audience]** 选项，您可以根据工作流的事件变量定义待定向受众的名称。有关更多信息，请参阅[此页面](../../automating/using/customizing-workflow-external-parameters.md)一节。

   ![](assets/readaudience_activity1.png)

1. 如果要对所选受众应用附加筛选，请通过该活动的 **[!UICONTROL Source filtering]** 选项卡添加条件。

   有关创建筛选条件的更多信息，请参阅[创建查询](../../automating/using/editing-queries.md#creating-queries)文档。

1. 确认活动的配置并保存工作流。
