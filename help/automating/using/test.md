---
title: 测试
description: 测试活动根据测试结果启用过渡。
page-status-flag: never-activated
uuid: 1562ec7a-253a-4f4f-b66a-c2948b57775a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 2650bf1f-0bce-4049-a226-2369f6666b95
context-tags: jstest,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51e98bb6212ad96d9c11b848df9dcad25b3f1b61
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 91%

---


# 测试{#test}

## 说明{#description}

![](assets/test.png)

该 **[!UICONTROL Test]** 活动根据测试结果启用过渡。

## 使用环境{#context-of-use}

**测试**&#x200B;活动可激活满足其关联条件的第一过渡。

如果未满足任何条件，且激活了&#x200B;**“使用默认过渡”**&#x200B;选项，则将激活默认过渡。

![](assets/wkf_test_activity_example.png)

条件可以基于&#x200B;**“函数”**，也可以基于&#x200B;**“变量”**，例如已声明插入到工作流 **[!UICONTROL External signal]** 活动中的事件变量。

**相关主题：**

* [函数列表](../../automating/using/list-of-functions.md)
* [使用外部参数调用工作流](../../automating/using/calling-a-workflow-with-external-parameters.md)

## 配置{#configuration}

1. 将 **[!UICONTROL Test]** 活动拖放到工作流中。
1. 选择活动，然后使用所显示快捷操作中的 ![](assets/edit_darkgrey-24px.png) 按钮将其打开。
1. 定义每个条件的属性：

   在编辑 **[!UICONTROL Condition]** 字段时，以下两个按钮有助于调用事件变量以及编辑组合变量和函数的表达式：

   * ![](assets/extsignal_picker.png):在工作流中可用的所有变量中选择事件变量(请参阅 [](../../automating/using/customizing-workflow-external-parameters.md))

      ![](assets/wkf_test_activity_variables.png)

   * ![](assets/extsignal_expression_editor.png)：编辑组合变量和函数的表达式。有关表达式编辑器的更多信息，请参阅[此章节](../../automating/using/advanced-expression-editing.md)。

      ![](assets/wkf_test_activity_variables_expression.png)
