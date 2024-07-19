---
title: 使用外部参数自定义工作流
description: 本节详细介绍如何使用外部参数调用工作流。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 8c1a47ed-3467-4fcd-8747-86f0e8f15cec
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 0%

---

# 使用外部参数自定义工作流 {#customizing-a-workflow-with-external-parameters}

触发工作流后，参数将摄取到事件变量中，并可用于自定义工作流的活动。

例如，它们可用于定义在&#x200B;**[!UICONTROL Read audience]**&#x200B;活动中要读取的受众、在&#x200B;**[!UICONTROL Transfer file]**&#x200B;活动中要传输的文件名称等。 （请参阅[此页面](../../automating/using/customizing-workflow-external-parameters.md)）。

## 使用事件变量 {#using-events-variables}

事件变量在必须遵循[标准语法](../../automating/using/advanced-expression-editing.md#standard-syntax)的表达式中使用。

使用事件变量的语法必须遵循以下格式，并使用已在&#x200B;**[!UICONTROL External signal]**&#x200B;活动中定义的参数名称（请参阅[在外部信号活动中声明参数](../../automating/using/declaring-parameters-external-signal.md)）：

```
$(vars/@parameterName)
```

在此语法中，**$**&#x200B;函数返回&#x200B;**字符串**&#x200B;数据类型。 如果要指定其他类型的数据，请使用以下函数：

* **$long**：整数。
* **$float**：十进制数。
* **$boolean**： true/false。
* **$datetime**： timestamp。

在活动中使用变量时，界面会提供调用变量的帮助。

![](assets/extsignal_callparameter.png)

* ![](assets/extsignal_picker.png)：从工作流中可用的所有变量中选择事件变量。

  ![](assets/wkf_test_activity_variables.png)

* ![](assets/extsignal_expression_editor.png)：编辑组合变量和函数的表达式（请参阅[此页面](../../automating/using/advanced-expression-editing.md)）。

  ![](assets/wkf_test_activity_variables_expression.png)

  此列表提供了可用于执行复杂筛选的功能。 [此部分](../../automating/using/list-of-functions.md)中详细介绍了这些函数。

  此外，您可以使用以下函数，这些函数在所有活动中都可用，从而允许您在使用外部参数调用工作流后使用事件变量（请参阅[此章节](../../automating/using/customizing-workflow-external-parameters.md#customizing-activities-with-events-variables)）：

  | 名称 | 说明 | 语法 |
  | ---------|----------|---------|
  | EndWith | 指示字符串（第1个参数）是否以特定字符串（第2个参数）结尾。 | EndWith（&lt;字符串>，&lt;字符串>） |
  | startWith | 指示字符串（第1个参数）是否以特定字符串（第2个参数）开头。 | startWith（&lt;字符串>，&lt;字符串>） |
  | Extract | 使用分隔符返回字符串的第一个字符。 | Extract（&lt;字符串>，&lt;分隔符>） |
  | ExtractRight | 使用分隔符返回字符串的最后一个字符。 | ExtractRight（&lt;字符串>，&lt;分隔符>） |
  | 日期格式 | 使用第2个参数中指定的格式来格式化日期（示例：&#39;%4Y%2M%2D&#39;） | DateFormat（&lt;日期>，&lt;格式>） |
  | 文件名 | 返回文件路径的名称。 | FileName（&lt;字符串>） |
  | FileExt | 返回文件路径的扩展名。 | FileExt（&lt;字符串>） |
  | GetOption | 返回指定函数的值。 | GetOption(&lt;optionName>) |
  | IsNull | 指示字符串或日期是否为null。 | IsNull（&lt;字符串/日期>） |
  | UrlUtf8编码 | 使用UTF8对URL进行编码。 | UrlUtf8Encode（&lt;字符串>） |

## 使用事件变量自定义活动 {#customizing-activities-with-events-variables}

事件变量可用于自定义多个活动，如下节中所列。 有关如何从活动调用变量的详细信息，请参阅[此部分](../../automating/using/customizing-workflow-external-parameters.md#using-events-variables)。

**[!UICONTROL Read audience]**&#x200B;活动：根据事件变量定义要定位的受众。 有关如何使用该活动的详细信息，请参阅[此部分](../../automating/using/read-audience.md)。

![](assets/extsignal_activities_audience.png)

**[!UICONTROL Test]**&#x200B;活动：基于事件变量生成条件。 有关如何使用该活动的详细信息，请参阅[此部分](../../automating/using/test.md)。

![](assets/extsignal_activities_test.png)

**[!UICONTROL Transfer file]**&#x200B;活动：根据事件变量自定义要传输的文件。 有关如何使用该活动的详细信息，请参阅[此部分](../../automating/using/transfer-file.md)。

![](assets/extsignal_activities_transfer.png)

**[!UICONTROL Query]**&#x200B;活动：可以使用组合事件变量和函数的表达式在查询中引用参数。 为此，请添加规则，然后单击&#x200B;**[!UICONTROL Advanced mode]**&#x200B;链接以访问表达式编辑窗口（请参阅[高级表达式编辑](../../automating/using/advanced-expression-editing.md)）。

有关如何使用该活动的详细信息，请参阅[此部分](../../automating/using/query.md)。

![](assets/extsignal_activities_query.png)

**[!UICONTROL Channels]**&#x200B;活动：根据事件变量对投放进行个性化设置。

>[!NOTE]
>
>每次准备投放时都会检索投放参数的值。
>
>定期投放准备基于投放&#x200B;**聚合期**。 例如，如果聚合期为“按天”，则每天只重新准备一次投放。 如果投放参数的值在当天被修改，则不会在投放中更新它，因为它已经准备过一次。
>
>如果您计划每天多次调用工作流，请使用[!UICONTROL No aggregation]选项，以便每次都更新投放参数。 有关定期投放配置的更多信息，请参阅[此章节](/help/automating/using/email-delivery.md#configuration)。

要根据事件变量对投放进行个性化，您必须首先在投放活动中声明要使用的变量：

1. 选择活动，然后单击![](assets/dlv_activity_params-24px.png)按钮以访问设置。
1. 选择&#x200B;**[!UICONTROL General]**&#x200B;选项卡，然后添加可用作投放中个性化字段的事件变量。

   ![](assets/extsignal_activities_delivery.png)

1. 单击 **[!UICONTROL Confirm]** 按钮。

现在，个性化字段列表中提供了已声明的事件变量。 您可以在投放中使用它们来执行以下操作：

* 定义用于投放的模板的名称。

  >[!NOTE]
  >
  >此操作仅适用于&#x200B;**定期**&#x200B;投放。

  ![](assets/extsignal_activities_template.png)

* 个性化投放：在选择个性化字段以配置投放时，**[!UICONTROL Workflow parameters]**&#x200B;元素中提供了事件变量。 您可以将它们用作任何个性化字段，例如，定义投放主题、发件人等。

  [此部分](../../designing/using/personalization.md)中详细介绍了投放个性化。

  ![](assets/extsignal_activities_perso.png)

**段代码**：根据事件变量定义段代码。

>[!NOTE]
>
>此操作可以从任何允许您定义段代码的活动中执行，例如&#x200B;**[!UICONTROL Query]**&#x200B;或&#x200B;**[!UICONTROL Segmentation]**&#x200B;活动。

![](assets/extsignal_activities_segment.png)

**投放标签**：根据事件变量定义投放标签。

![](assets/extsignal_activities_label.png)
