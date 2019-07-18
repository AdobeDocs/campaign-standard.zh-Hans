---
title: 外部信号
seo-title: 外部信号
description: 外部信号
seo-description: 在其他工作流中成功满足某些条件时，外部信号活动会触发工作流。
page-status-flag: 从未激活
uuid: 884b6daf-bfd9-440b-836-004b80 c76 def
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 执行活动
discoiquuid: 911c71b5-da8 b-4916-b645-13bba6 d21715
context-tags: 信号，主信号
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# External signal{#external-signal}

## Description {#description}

![](assets/signal.png)

**[!UICONTROL External signal]** 当在另一个工作流中或从REST API调用成功满足某些条件时，活动会触发工作流。

## Context of use {#context-of-use}

**[!UICONTROL External signal]** 该活动用于组织和编排属于同一客户旅程的不同流程的不同流程。它允许从另一个工作流程开始工作流，从而支持更复杂的客户旅程，同时能够更好地监控和应对问题。

**[!UICONTROL External signal]** 活动被设计为工作流的第一个活动。It can be triggered from the **[!UICONTROL End]** activity of another workflow or from a REST API call (for more on this, refer to the [API documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#triggering-a-signal-activity) ).

触发后，可以定义外部参数并在工作流事件变量中可用。The process to call a workflow with external parameters is detailed in [this section](../../automating/using/calling-a-workflow-with-external-parameters.md).

>[!NOTE]
>
>活动的触发频率不能超过10分钟。

Note that an **[!UICONTROL External signal]** activity can be triggered from several different events. In that case, the **[!UICONTROL External signal]** is triggered as soon as one of the source workflows or API call is executed. 它并不要求所有源工作流都已完成。

## Configuration {#configuration}

When configuring an external signal, it is important to first configure the **[!UICONTROL External signal]** activity in the destination workflow. Once this configuration is done, the **[!UICONTROL External signal]** activity of this workflow becomes available to configure the **[!UICONTROL End]** activity of the source workflow.

1. Drag and drop an **[!UICONTROL External signal]** activity into your destination workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. 编辑活动的标签。This label is needed when configuring the source workflow that triggers the **[!UICONTROL External signal]**.

   If you want to call the workflow with parameters, use the **[!UICONTROL Parameters]** area to declare them. For more on this, refer to [this section](../../automating/using/calling-a-workflow-with-external-parameters.md#declaring-the-parameters-in-the-external-signal-activity).

   ![](assets/external_signal_configuration.png)

1. 确认活动的配置，添加所需的任何其他活动并保存工作流。

   >[!NOTE]
   >
   >如果要从其他工作流触发目标工作流，请继续执行以下步骤。If you want to trigger the destination workflow from a REST API call, consult the [API documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#triggering-a-signal-activity) to get more details.

1. Open the source workflow and select an **[!UICONTROL End]** activity. If there is no **[!UICONTROL End]** activity available, add one after the last activity of a branch of the workflow.

   默认情况下，某些活动没有任何出站过渡。From the **[!UICONTROL Properties]** tab of these activities, you can add an outbound transition.

   For example, in an **[!UICONTROL Update data]** activity, go to the **[!UICONTROL Transitions]** tab and check the **[!UICONTROL Add an outbound transition without the population]** option. 此选项允许添加不包含任何数据且不占用系统中不必要的空间的过渡。It is just used to connect the extra **[!UICONTROL End]** activity that triggers the destination workflow.

   ![](assets/external_signal_empty_transition.png)

1. In the **[!UICONTROL External signal]** tab of the **[!UICONTROL End]** activity, select the destination workflow as well as the **[!UICONTROL External signal]** activity to trigger within that workflow.

   When you set an **[!UICONTROL End]** activity to trigger another workflow, its icon is updated with an additional signal symbol.

   If you want to call the workflow with parameters, use the **[!UICONTROL Parameters and values]** area. For more on this, refer to [this section](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow).

   ![](assets/external_signal_end.png)

1. 保存源工作流。

Once the **[!UICONTROL End]** activity of the source workflow or the REST API call is executed, the destination workflow is automatically triggered from the **[!UICONTROL External signal]** activity.

>[!NOTE]
>
>必须手动启动目标工作流，然后才能触发该工作流。When started, the **[!UICONTROL External activity]** is activated and waits for the signal from the source workflow.

## Example {#example}

The following example illustrates the **[!UICONTROL External signal]** activity in a typical use case. 数据导入在源工作流中执行。完成导入并更新数据库后，将触发第二个工作流。第二个工作流用于更新导入数据的集合。

源工作流显示如下：

* [加载文件](../../automating/using/load-file.md) 活动会上传包含新购买数据的文件。Note that the [database has been extended](../../developing/using/data-model-concepts.md) accordingly as purchase data are not present by default in the datamart.

   例如：

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2015;dannymars@example.com;A2;799
   aze124;28/05/2015;dannymars@example.com;A7;8
   aze125;31/07/2015;john.smith@example.com;A7;8
   aze126;14/12/2015;john.smith@example.com;A10;4
   aze127;02/01/2016;dannymars@example.com;A3;79
   aze128;04/03/2016;clara.smith@example.com;A8;149
   ```

* [对帐](../../automating/using/reconciliation.md) 活动创建导入的数据与数据库之间的链接，以便事务数据正确连接到配置文件和产品。
* [更新数据](../../automating/using/update-data.md) 活动会插入并更新数据库的事务处理资源与传入数据。
* **[!UICONTROL End]** 活动触发了用于更新集合的目标工作流。

![](assets/signal_example_source1.png)

目标工作流如下所示：

* **[!UICONTROL External signal]** 活动等待源工作流成功完成。
* [查询](../../automating/using/query.md#enriching-data) 活动定位配置文件，并将其丰富的集合设置为检索上次购买日期。
* [更新数据](../../automating/using/update-data.md) 活动将额外数据存储在专用自定义字段中。Note that the profile resource has been extended to add the **Last purchase date** field.

![](assets/signal_example_source2.png)

