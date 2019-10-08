---
title: 使用外部参数调用工作流
seo-title: 使用外部参数调用工作流
description: 使用外部参数调用工作流
seo-description: 本节详细介绍如何使用外部参数调用工作流。
page-status-flag: 从未激活
uuid: beccd1b6-8e6d-4504-9152-9ff537459c4a
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 自动化
content-type: 参考
topic-tags: 工作流——一般操作
discoiquuid: 1676da91-55e3-414f-bcd3-bb0804b682bd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 94c7649448aff859daaf2bbe9a4d17a5187ac71f

---


# 使用外部参数调用工作流{#calling-a-workflow-with-external-parameters}

Campaign standard允许您调用包含参数（受众名称要定位、要导入的文件名称、消息内容的一部分等）的工作流。 这样，您便可以轻松地将Campaign自动化与外部系统集成。

让我们举一个例子，我们希望从CMS直接发送电子邮件。 在这种情况下，您可以配置系统以选择受众并将内容通过电子邮件发送到CMS。 单击发送后，将使用这些参数调用营销活动工作流，以便您在工作流中使用这些参数来定义要在分发中使用的受众和URL内容。

使用参数调用工作流的过程如下：

1. 在活动中声明参 **[!UICONTROL External signal]** 数。 请参 [阅在外部信号活动中声明参数](../../automating/using/calling-a-workflow-with-external-parameters.md#declaring-the-parameters-in-the-external-signal-activity)。
1. 配置活 **[!UICONTROL End]** 动或API调用以定义参数并触发工作流 **[!UICONTROL External signal]** 活动。

触发工作流后，这些参数将被引入工作流的事件变量中，并可在工作流中使用。 请参 [阅使用外部参数自定义工作流](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-a-workflow-with-external-parameters)。

![](assets/extsignal_process.png)

## 在外部信号活动中声明参数 {#declaring-the-parameters-in-the-external-signal-activity}

使用参数调用工作流的第一步是在活动中声明这 **[!UICONTROL External signal]** 些参数。

1. 打开活 **[!UICONTROL External signal]** 动，然后选择选 **[!UICONTROL Parameters]** 项卡。
1. 单击该 **[!UICONTROL Create element]** 按钮，然后指定每个参数的名称和类型。

   >[!CAUTION]
   >
   >确保参数的名称和数量与调用工作流时定义的参数相同(请参阅 [在调用工作流时定义参数](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow))。 此外，参数类型必须与期望值一致。

   ![](assets/extsignal_declaringparameters_1.png)

1. 声明参数后，完成工作流配置，然后运行它。

## 在调用工作流时定义参数 {#defining-the-parameters-when-calling-the-workflow}

本节详细介绍了在调用工作流时如何定义参数。 有关如何通过API调用执行此操作的详细信息，请参阅 [REST API文档](https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html)。

在定义参数之前，请确保：

* 参数已在活动中声 **[!UICONTROL External Signal]** 明。 请参 [阅在外部信号活动中声明参数](../../automating/using/calling-a-workflow-with-external-parameters.md#declaring-the-parameters-in-the-external-signal-activity)。
* 包含信号活动的工作流正在运行。

要配置活 **[!UICONTROL End]** 动，请执行以下步骤：

1. 打开活 **[!UICONTROL End]** 动，然后选择选 **[!UICONTROL External signal]** 项卡。
1. 选择要调用的工作流和外部信号活动。
1. 单击 **[!UICONTROL Create element]** 按钮以添加参数，然后填写其名称和值。

   * **[!UICONTROL Name]**:已在活动中声明的名称(请参 **[!UICONTROL External signal]** 阅在“外 [部信号”活动中声明参数](../../automating/using/calling-a-workflow-with-external-parameters.md#declaring-the-parameters-in-the-external-signal-activity))。
   * **[!UICONTROL Value]**:要分配给参数的值。 该值应遵循本节 **中所述的**“标准 [”语法](../../automating/using/advanced-expression-editing.md#standard-syntax)。
   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >确保在活动中声明了所有参 **[!UICONTROL External signal]** 数。 否则，运行活动时将发生错误。

1. 定义参数后，确认活动，然后保存工作流。

## 监视事件变量 {#monitoring-the-events-variables}

可以监视工作流中可用的事件变量，包括声明的外部参数。 为此请执行以下操作步骤：

1. 选择活动后面的活 **[!UICONTROL External signal]** 动，然后单击按 **[!UICONTROL Log and tasks]** 钮。
1. 在选项卡 **[!UICONTROL Tasks]** 中，单击 ![](assets/edit_darkgrey-24px.png) 按钮。

   ![](assets/extsignal_monitoring_2.png)

1. 此时会显示任务的执行上下文（ID、状态、持续时间等），包括现在可用于工作流的所有事件变量。

   ![](assets/extsignal_monitoring_3.png)

## 使用外部参数自定义工作流 {#customizing-a-workflow-with-external-parameters}

触发工作流后，这些参数将被引入事件变量中，并可用于自定义工作流的活动。

例如，它们可用于定义在活动中要阅读的受众、在活 **[!UICONTROL Read audience]** 动中要传输的文件的名 **[!UICONTROL Transfer file]** 称等。

可使用事件变量自定义的活动在本节中有 [详细介绍](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables)。

### 使用事件变量 {#using-events-variables}

事件变量在必须遵守标准语法的表达式中 **[使用](../../automating/using/advanced-expression-editing.md#standard-syntax)**。

使用事件变量的语法必须遵循以下格式，并使用在活动中定义的参数名 **[!UICONTROL External signal]** 称(请参 [阅在外部信号活动中声明参数](../../automating/using/calling-a-workflow-with-external-parameters.md#declaring-the-parameters-in-the-external-signal-activity)):

```
$(vars/@parameterName)
```

在此语法中， **$** 函数返回 **字符串** 数据类型。 如果要指定其他类型的数据，请使用以下函数：

* **$long**:整数。
* **$float**:小数。
* **$boolean**:true/false。
* **$datetime**:时间戳。

在活动中使用变量时，界面会提供调用该变量的帮助。

![](assets/extsignal_callparameter.png)

* ![](assets/extsignal_picker.png):在工作流中可用的所有变量中选择事件变量（请参阅）。

   ![](assets/wkf_test_activity_variables.png)

* ![](assets/extsignal_expression_editor.png):编辑组合变量和函数的表达式。 有关表达式编辑器的详细信息，请参 [阅此部分](../../automating/using/advanced-expression-editing.md)。

   ![](assets/wkf_test_activity_variables_expression.png)

**相关主题：**

* [编辑表达式](../../automating/using/advanced-expression-editing.md#edit-an-expression)
* [标准语法](../../automating/using/advanced-expression-editing.md#standard-syntax)
* [函数列表](../../automating/using/list-of-functions.md)

### 使用事件变量自定义活动 {#customizing-activities-with-events-variables}

事件变量可用于自定义多个活动，如下面的部分中列出。 有关如何从活动调用变量的详细信息，请参阅 [此部分](../../automating/using/calling-a-workflow-with-external-parameters.md#using-events-variables)。

**[!UICONTROL Read audience]** 活动：根据事件变量定义受众以定位。

有关如何使用活动的详细信息，请参阅专 [用部分](../../automating/using/read-audience.md)。

![](assets/extsignal_activities_audience.png)

**[!UICONTROL Test]** 活动：根据事件变量构建条件。

有关如何使用活动的详细信息，请参阅专 [用部分](../../automating/using/test.md)。

![](assets/extsignal_activities_test.png)

**[!UICONTROL Transfer file]** 活动：根据事件变量自定义要传输的文件。

有关如何使用活动的详细信息，请参阅专 [用部分](../../automating/using/transfer-file.md)。

![](assets/extsignal_activities_transfer.png)

**[!UICONTROL Query]** 活动：通过使用组合事件变量和函数的表达式，可以在查询中引用参数。 为此，请添加一个规则，然后单击链 **[!UICONTROL Advanced mode]** 接以访问表达式编辑窗口(请参阅高 [级表达式编辑](../../automating/using/advanced-expression-editing.md))。

有关如何使用活动的详细信息，请参阅专 [用部分](../../automating/using/query.md)。

![](assets/extsignal_activities_query.png)

**[!UICONTROL Channels]** 活动：根据事件变量个性化交付。

>[!NOTE]
>
>每次准备递送时，检索递送参数的值。
>
>重复交付准备基于交付汇总 **期**。 例如，如果汇总期间为“按天”，则每天只重新准备一次交付。 如果在一天中修改了交付参数的值，则交付中不会更新它，因为它已准备一次。
>
>如果您计划每天多次调用工作流，请使 [!UICONTROL No aggregation] 用选项，以便每次都更新传送参数。 有关重复提交配置的详细信息，请参阅 [此部分](/help/automating/using/email-delivery.md#configuration)。

要根据事件变量对分发进行个性化设置，您必须首先在分发活动中声明要使用的变量：

1. 选择活动，然后单击 ![](assets/dlv_activity_params-24px.png) 按钮以访问设置。
1. 选择选 **[!UICONTROL General]** 项卡，然后添加事件变量，这些变量将作为分发中的个性化字段可用。

   ![](assets/extsignal_activities_delivery.png)

1. Click the **[!UICONTROL Confirm]** button.

声明的事件变量现在可从个性化字段列表中使用。 您可以在交货中使用它们来执行以下操作：

* 定义要用于分发的模板的名称。

   >[!NOTE]
   >
   >此操作仅可用于 **重复** 提交。

   ![](assets/extsignal_activities_template.png)

* 个性化交付：在选择个性化字段以配置分发时，事件变量在元素中可 **[!UICONTROL Workflow parameters]** 用。 您可以将它们用作任何个性化字段，例如定义交付主体、发送方等。

   本节详细介绍了交 [付个性化](../../designing/using/personalization.md)。

   ![](assets/extsignal_activities_perso.png)

**区段代码**:根据事件变量定义区段代码。

>[!NOTE]
>
>此操作可从允许您定义区段代码（例如，活动）的任何活动中执 **[!UICONTROL Query]** 行 **[!UICONTROL Segmentation]** 。

![](assets/extsignal_activities_segment.png)

**传送标签**:根据事件变量定义交付标签。

![](assets/extsignal_activities_label.png)

## 用例 {#use-case}

以下用例说明如何使用工作流中的参数调用工作流。

其目标是使用外部参数从API调用触发工作流。 此工作流将从文件将数据加载到数据库中并创建关联的受众。 创建受众后，将触发第二个工作流以发送消息个性化，该消息使用API调用中定义的外部参数。

要执行此用例，您需要执行以下操作：

1. **进行API调用** ，以使用外部参数触发Workflow 1。 请参 [阅步骤1:配置API调用](../../automating/using/calling-a-workflow-with-external-parameters.md#step-1--configuring-the-api-call)。
1. **构建工作流1**:该工作流将传输一个文件并将其加载到数据库中。 然后，它将测试数据是否为空，并最终将档案保存到受众中。 最后，它将触发Workflow 2。 请参 [阅第2步：配置工作流1](../../automating/using/calling-a-workflow-with-external-parameters.md#step-2--configuring-workflow-1)。
1. **构建工作流2**:该工作流将读取在工作流1中创建的受众，然后向配置文件发送个性化消息，并使用参数自定义区段代码。 请参 [阅第3步：配置工作流2](../../automating/using/calling-a-workflow-with-external-parameters.md#step-3--configuring-workflow-2)。

![](assets/extsignal_uc_process.png)

### 先决条件 {#prerequisites}

在配置工作流之前，您需要创建工作流1和2，其中 **[!UICONTROL External signal]** 每个工作流都包含活动。 这样，您就可以在调用工作流时定位这些信号活动。

### 第1步：配置API调用 {#step-1--configuring-the-api-call}

进行API调用以触发包含参数的Workflow 1。 有关API调用语法的详细信息，请参阅 [Campaign Standard REST API文档](https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html)。

在我们的例子中，我们希望使用以下参数调用工作流：

* **fileToTarget**:要导入到数据库的文件的名称。
* **折扣设计**:要在折扣中显示的描述。

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/<TRIGGER_URL>
-H 'Authorization: Bearer <ACCESS_TOKEN>' 
-H 'Cache-Control: no-cache' 
-H 'X-Api-Key: <API_KEY>' 
-H 'Content-Type: application/json;charset=utf-8' 
-H 'Content-Length:79' 
-i
-d {
-d "source:":"API",
-d "parameters":{
-d "fileToTarget":"profile.txt",
-d "discountDesc":"Running shoes"
-d } 
```

### 第2步：配置工作流1 {#step-2--configuring-workflow-1}

工作流1的构建如下：

* **[!UICONTROL External signal]** 活动：其中必须声明外部参数才能在工作流中使用。
* **[!UICONTROL Transfer file]** 活动：导入具有参数中定义的名称的文件。
* **[!UICONTROL Load file]** 活动：将数据从导入的文件加载到数据库中。
* **[!UICONTROL Update data]** 活动：使用导入的文件中的数据插入或更新数据库。
* **[!UICONTROL Test]** 活动：检查是否导入了数据。
* **[!UICONTROL Save audience]** 活动：如果文件包含数据，则将档案保存到受众中。
* **[!UICONTROL End activity]** 活动：调用工作流2及要在其中使用的参数。

![](assets/extsignal_uc_wkf1.png)

请按照以下步骤配置工作流：

1. 声明在API调用中定义的参数。 为此，请打开活 **[!UICONTROL External signal]** 动，然后添加参数的名称和类型。

   ![](assets/extsignal_uc1.png)

1. 添加活 **[!UICONTROL Transfer file]** 动以将数据导入数据库。要执行此操作，请拖放活动，打开它，然后选择选 **[!UICONTROL Protocol]** 项卡。
1. 选择 **[!UICONTROL Use a dynamic file path]** 选项，然后使 **** 用fileToTarget参数作为要传输的文件：

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc2.png)

1. 将数据从文件加载到数据库中。

   为此，请将活动拖放到 **[!UICONTROL Load file]** 工作流中，然后根据需要对其进行配置。

1. 插入数据库并用导入文件中的数据更新数据库。

   为此，请拖放活动，然 **[!UICONTROL Update data]** 后选择选项卡以添 **[!UICONTROL Identification]** 加对帐条件(在我们的例子中为电子邮件 **字段** )。

   ![](assets/extsignal_uc3.png)

1. 选择选 **[!UICONTROL Fields to update]** 项卡，然后指定要在数据库中更新的字段(在我们的例子中为名 **字** 和电子 **邮件字段** )。

   ![](assets/extsignal_uc4.png)

1. 检查是否从文件检索数据。 为此，请将活动拖放到工 **[!UICONTROL Test]** 作流中，然后单击按钮以 **[!UICONTROL Add an element]** 添加一个条件。
1. 命名并定义条件。 在我们的例子中，我们希望测试出站过渡是否包含具有以下语法的数据：

   ```
   $long(vars/@recCount)>0
   ```

   ![](assets/extsignal_uc5.png)

1. 如果检索到数据，则将其保存到受众中。 为此，请向Target添加 **[!UICONTROL Save audience]** 活动(而 **非空过渡** )，然后打开它。
1. 选择 **[!UICONTROL Use a dynamic label]** 选项，然后使用 **** fileToTarget参数作为受众的标签：

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc6.png)

1. 拖放将使用参 **[!UICONTROL End]** 数调用工作流2的活动，然后打开它。
1. 选择选 **[!UICONTROL External signal]** 项卡，然后指定要触发的工作流及其关联的信号活动。
1. 定义要在Oracle Workflow 2中使用的参数及其关联值。

   在我们的情况下，我们希望传递最初在API调用中定义的参数(**fileToTarget** and **discountDesc**)，以及一个具有常数值的 **segmentCode** （“20%折扣”）的附加参数。

   ![](assets/extsignal_uc7.png)

工作流1已配置，您现在可以构建工作流2。 如需详细信息，请参阅[此部分](../../automating/using/calling-a-workflow-with-external-parameters.md#step-3--configuring-workflow-2)。

### 第3步：配置工作流2 {#step-3--configuring-workflow-2}

工作流2的构建如下：

* **[!UICONTROL External signal]** 活动：其中必须声明参数才能在工作流中使用。
* **[!UICONTROL Read audience]** 活动：读取在工作流1中保存的受众。
* **[!UICONTROL Email delivery]** 活动：向目标受众发送重复消息，并使用参数进行个性化。

![](assets/extsignal_uc_wkf2.png)

请按照以下步骤配置工作流：

1. 声明已在工作流1中定义的参数。

   为此，请打开活 **[!UICONTROL External signal]** 动，然后添加在Workflow 1的活动中定义的每个参数的名 **[!UICONTROL End]** 称和类型。

   ![](assets/extsignal_uc8.png)

1. 使用已保存在Workflow 1中的受众。 为此，请将活动拖放到工 **[!UICONTROL Read audience]** 作流中，然后打开它。
1. 选择 **[!UICONTROL Use a dynamic audience]** 选项，然后使用 **** fileToTarget参数作为要读取的受众的名称：

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc9.png)

1. 根据segmentCode参数命名出站 **过渡** 。

   为此，请选择选 **[!UICONTROL Transition]** 项卡，然后选择 **[!UICONTROL Use a dynamic segment code]** 选项。

1. 使用 **segmentCode** 参数作为出站过渡的名称：

   ```
   $(vars/@segmentCode)
   ```

   ![](assets/extsignal_uc10.png)

1. 拖放活动 **[!UICONTROL Email delivery]** 以向受众发送消息。
1. 确定消息中使用的参数，以便使用discountDesc参数对其进 **行个性化** 。 为此，请打开活动的高级选项，然后添加参数名和值。

   ![](assets/extsignal_uc10b.png)

1. 您现在可以配置消息。 打开活动，然后选择 **[!UICONTROL Recurring email]**。

   ![](assets/extsignal_uc11.png)

1. 选择要使用的模板，然后根据您的需求定义电子邮件属性。
1. 将discountDesc **参数用作** “个性化”字段。 为此，请从个性化字段列表中选择它。

   ![](assets/extsignal_uc13.png)

1. 您现在可以完成消息的配置，然后照常发送。

   ![](assets/extsignal_uc14.png)

### 执行工作流 {#executing-the-workflows}

构建工作流后，您可以执行这些工作流。 在执行API调用之前，请确保启动了两个工作流。
