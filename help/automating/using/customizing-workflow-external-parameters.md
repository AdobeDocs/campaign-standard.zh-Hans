---
solution: Campaign Standard
product: campaign
title: 使用外部参数调用工作流
description: 本节详细介绍了如何使用外部参数调用工作流。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '817'
ht-degree: 1%

---


# 使用外部参数{#customizing-a-workflow-with-external-parameters}自定义工作流

触发工作流后，这些参数将被引入事件变量中，并可用于自定义工作流的活动。

例如，它们可用于定义在&#x200B;**[!UICONTROL Read audience]**&#x200B;活动中读取的受众、在&#x200B;**[!UICONTROL Transfer file]**&#x200B;活动中传输的文件名等。 （请参阅[此页](../../automating/using/customizing-workflow-external-parameters.md)）。

## 使用事件变量{#using-events-variables}

事件变量在必须遵循[标准语法](../../automating/using/advanced-expression-editing.md#standard-syntax)的表达式中使用。

使用事件变量的语法必须采用以下格式，并使用在&#x200B;**[!UICONTROL External signal]**&#x200B;活动中定义的参数名(请参阅[在外部信号活动](../../automating/using/declaring-parameters-external-signal.md)中声明参数):

```
$(vars/@parameterName)
```

在此语法中，**$**&#x200B;函数返回&#x200B;**string**&#x200B;数据类型。 如果要指定其他类型的数据，请使用以下函数：

* **$long**:整数。
* **$float**:小数。
* **$boolean**:true/false。
* **$datetime**:时间戳。

在活动中使用变量时，界面会提供调用该变量的帮助。

![](assets/extsignal_callparameter.png)

* ![](assets/extsignal_picker.png):在工作流中可用的所有变量中选择事件变量。

   ![](assets/wkf_test_activity_variables.png)

* ![](assets/extsignal_expression_editor.png):编辑组合变量和函数的表达式(请 [参阅本页](../../automating/using/advanced-expression-editing.md))。

   ![](assets/wkf_test_activity_variables_expression.png)

   此列表提供允许您执行复杂过滤的函数。 这些函数在[本节](../../automating/using/list-of-functions.md)中有详细说明。

   此外，您还可以使用以下函数，这些函数在所有活动中都可用，这些函数允许您在调用具有外部参数的工作流后使用事件变量（请参阅[本节](../../automating/using/customizing-workflow-external-parameters.md#customizing-activities-with-events-variables)）：

   | 名称 | 说明 | 语法 |
   ---------|----------|---------
   | 结束方式 | 指示字符串（第1个参数）是否以特定字符串（第2个参数）结尾。 | EndWith(&lt;String>,&lt;String>) |
   | startWith | 指示字符串（第1个参数）是否开始了特定字符串（第2个参数）。 | startWith(&lt;String>,&lt;String>) |
   | Extract | 使用分隔符返回字符串的第一个字符。 | Extract(&lt;String>,&lt;Separator>) |
   | ExtractRight | 使用分隔符返回字符串的最后一个字符。 | ExtractRight(&lt;String>,&lt;Separator>) |
   | DateFormat | 使用在第2个参数中指定的格式设置日期格式(示例： “%4Y%2M%2D”) | DateFormat(&lt;Date>,&lt;Format>) |
   | 文件名 | 返回文件路径的名称。 | FileName(&lt;String>) |
   | FileExt | 返回文件路径的扩展名。 | FileExt(&lt;String>) |
   | GetOption | 返回指定函数的值。 | GetOption(&lt;optionName>) |
   | IsNull | 指示字符串或日期是否为null。 | IsNull(&lt;String/date>) |
   | URLUtf8编码 | 以UTF8对URL进行编码。 | UrlUtf8Encode(&lt;String>) |

## 使用事件变量{#customizing-activities-with-events-variables}自定义活动

事件变量可用于自定义多个活动，如下面部分所列。 有关如何从活动调用变量的详细信息，请参阅[本节](../../automating/using/customizing-workflow-external-parameters.md#using-events-variables)。

**[!UICONTROL Read audience]** 活动:根据事件变量定义受众到目标。有关如何使用活动的详细信息，请参阅[本节](../../automating/using/read-audience.md)。

![](assets/extsignal_activities_audience.png)

**[!UICONTROL Test]** 活动:根据事件变量构建条件。有关如何使用活动的详细信息，请参阅[本节](../../automating/using/test.md)。

![](assets/extsignal_activities_test.png)

**[!UICONTROL Transfer file]** 活动:根据事件变量自定义要传输的文件。有关如何使用活动的详细信息，请参阅[本节](../../automating/using/transfer-file.md)。

![](assets/extsignal_activities_transfer.png)

**[!UICONTROL Query]** 活动:通过使用组合事件变量和函数的表达式，可以在查询中引用参数。为此，请添加一个规则，然后单击&#x200B;**[!UICONTROL Advanced mode]**&#x200B;链接以访问表达式编辑窗口(请参阅[高级表达式编辑](../../automating/using/advanced-expression-editing.md))。

有关如何使用活动的详细信息，请参阅[本节](../../automating/using/query.md)。

![](assets/extsignal_activities_query.png)

**[!UICONTROL Channels]** 活动:根据投放变量对事件进行个性化。

>[!NOTE]
>
>每次准备投放时，都检索投放参数的值。
>
>循环投放准备基于投放&#x200B;**聚合周期**。 例如，如果汇总期间为“按天”，则投放将每天仅重新准备一次。 如果在一天中修改了投放参数的值，则投放中不会更新它，因为它已经准备了一次。
>
>如果您计划每天多次调用工作流，请使用[!UICONTROL No aggregation]选项，以便每次更新投放参数。 有关循环投放配置的详细信息，请参阅[本节](/help/automating/using/email-delivery.md#configuration)。

要根据事件变量对投放进行个性化设置，必须首先在投放活动中声明要使用的变量：

1. 选择活动，然后单击![](assets/dlv_activity_params-24px.png)按钮以访问设置。
1. 选择&#x200B;**[!UICONTROL General]**&#x200B;选项卡，然后添加事件变量，这些变量将作为个性化字段在投放中可用。

   ![](assets/extsignal_activities_delivery.png)

1. 单击 **[!UICONTROL Confirm]** 按钮。

声明的事件变量现在可从个性化字段的列表中使用。 您可以在投放中使用它们执行以下操作：

* 定义要用于投放的模板的名称。

   >[!NOTE]
   >
   >此操作仅适用于&#x200B;**重复**&#x200B;投放。

   ![](assets/extsignal_activities_template.png)

* 个性化投放:在选择个性化字段以配置投放时，**[!UICONTROL Workflow parameters]**&#x200B;元素中提供了事件变量。 您可以将它们用作任何个性化字段，例如定义投放主题、发送者等。

   投放个性化详见[本节](../../designing/using/personalization.md)。

   ![](assets/extsignal_activities_perso.png)

**段代码**:根据段代码变量定义事件。

>[!NOTE]
>
>此操作可以从任何允许您定义段代码(例如&#x200B;**[!UICONTROL Query]**&#x200B;或&#x200B;**[!UICONTROL Segmentation]**&#x200B;活动)的活动执行。

![](assets/extsignal_activities_segment.png)

**投放标签**:根据投放变量定义事件标签。

![](assets/extsignal_activities_label.png)
