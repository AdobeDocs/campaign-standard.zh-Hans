---
title: Test
seo-title: Test
description: Test
seo-description: 测试活动可基于测试结果启用过渡。
page-status-flag: 从未激活
uuid: 1562ec7a-253a-4f4f66a-c2948 b57775 a
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 执行活动
discoiquuid: 2650bf1f-049-a226-2369f6666 b95
context-tags: 主要，主要
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Test{#test}

## Description {#description}

![](assets/test.png)

**[!UICONTROL Test]** 活动将根据测试结果启用过渡。

## Context of use {#context-of-use}

**测试** 活动激活满足与与之关联的条件的第一个过渡。

If no condition is satisfied and if the **Use default transition** option is activated, a default transition will be activated.

![](assets/wkf_test_activity_example.png)

Conditions can be based on **functions**, or on **variables**, for example events variables that have been declared into the workflow's **[!UICONTROL External signal]** activity.

**相关主题：**

* [函数列表](../../automating/using/list-of-functions.md)
* [使用外部参数调用工作流](../../automating/using/calling-a-workflow-with-external-parameters.md)

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Test]** activity into the workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. 定义每个条件的属性：

   When editing the **[!UICONTROL Condition]** field, two buttons provide help to call events variables and edit expressions combining variables and functions:

   * ![](assets/extsignal_picker.png)：在工作流中可用的所有变量之间选择事件变量(请参阅 [使用外部参数自定义工作流](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-a-workflow-with-external-parameters))

      ![](assets/wkf_test_activity_variables.png)

   * ![](assets/extsignal_expression_editor.png)：编辑变量和函数的表达式。For more on the Expression editor, refer to [this section](../../automating/using/advanced-expression-editing.md).

      ![](assets/wkf_test_activity_variables_expression.png)

