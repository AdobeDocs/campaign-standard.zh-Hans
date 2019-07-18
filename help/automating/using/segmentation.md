---
title: 分段
seo-title: 分段
description: 分段
seo-description: 分段活动允许您根据之前放置在工作流中的活动计算出的人群，创建一个或多个区段。
page-status-flag: 从未激活
uuid: 77796f18-design5-4e7 a-9d7 b-4d0 dd8943 bf
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 定位活动
discoiquuid: 0cr9d02-772e-406b-874a-5381dd0c8709
context-tags: 细分，主要
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Segmentation{#segmentation}

## Description {#description}

![](assets/segmentation.png)

The **[!UICONTROL Segmentation]** activity lets you create one or several segments from a population calculated by activities placed earlier in the workflow. 在活动结束时，可以在一个过渡或不同的过渡中处理它们。

>[!NOTE]
>
>默认情况下，入站人群的成员只能属于一个区段。过滤器会根据活动中区段的顺序进行应用。

## Context of use {#context-of-use}

**[!UICONTROL Segmentation]** 活动通常位于定位活动(查询、交叉点、联合、排除等)之后。以定义区段构成的标准人群。

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Segmentation]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Select the **[!UICONTROL Resource type]** on which the segmentation has to be carried out:

   * **[!UICONTROL Database resource]** 如果对数据库中已经存在的数据执行分段。Select the **[!UICONTROL Filtering dimension]** depending on the data that you want to segment. By default, segmentation is carried out on the **profiles**.
   * **[!UICONTROL Temporary resource]** 如果对工作流的临时数据进行分段：选择 **[!UICONTROL Targeted set]** 包含要区段的数据。导入文件或数据库中的数据被丰富后，可能会遇到此用例。

1. 选择要使用的出站过渡类型：

   * **[!UICONTROL Generate one transition per segment]**：在活动结束时，为每个已配置的区段添加一个出站过渡。
   * **[!UICONTROL Generate all segments in one transition]**：所有配置的区段都会重新嵌入到一个出站过渡中。指定过渡标签。每个区段的成员保留已分配给它们的区段代码。

1. Add a segment by using the ![](assets/add_darkgrey-24px.png) or **[!UICONTROL Add an element]** button and specify the standard properties:

   * **[!UICONTROL Do not activate the transition if the population is empty]**：只有在检索数据后，才会启用区段。
   * **[!UICONTROL Filter initial population (query)]**：可让您筛选此区段的人口。
   * **[!UICONTROL Limit segment population]**：允许您限制区段大小。
   * **[!UICONTROL Filter and limit segment population]**：允许您筛选区段人群并限制其大小。
   * **[!UICONTROL Label]**：区段标签。
   * **[!UICONTROL Segment code]**：分配给区段人群的代码。可以使用标准表达式和事件变量个性化区段代码(请参阅 [使用事件变量自定义活动](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables))。
   * **[!UICONTROL Exclude segment from population]**：允许您从活动的出站人群中排除指定的区段。This option can only be used if the **[!UICONTROL Generate all segments in the same transition]** option is selected.
   ![](assets/wkf_segment_new_segment.png)

1. 打开区段的详细信息视图以访问后者的配置选项。To do this, check the relevant box in the activity's segment list, then select ![](assets/wkf_segment_parameters_24px.png).
1. If the option to filter the initial population is checked, open the **[!UICONTROL Filter]** tab and specify your segment's population. 过滤器基于在步骤中选择的过滤维度。Consult the [Query editing](../../automating/using/editing-queries.md) section for further information on population filtering.

   如果对临时资源执行分段，则此选项卡中不提供人数和预览人数。

1. If the option to limit the segment size is checked, open the **[!UICONTROL Limitation]** tab.

   First, select the **[!UICONTROL Type of limit]** that you would like to use:

   * **[!UICONTROL Random sampling]**：根据需要随机考虑 **[!UICONTROL Filter]** 选项卡的配置，随机选择区段人群。
   * **[!UICONTROL Ordered sampling]**：区段人群以有序方式进行选择。您必须最终指定要考虑的列以及要应用的排序类型。For example, if you select the **Age** field as the sort column while applying a **[!UICONTROL Descending sort]** and setting a limit of 100, only the profiles of the top 100 oldest people will be kept.
   Now specify the size **[!UICONTROL Limit]** of the segment:

   * **[!UICONTROL Size (as a % of the initial population)]**：使用活动的初始人口百分比来指定区段大小。
   * **[!UICONTROL Maximum size]**：为区段人群指定最大成员人数。
   * **[!UICONTROL By data grouping]**：您可以根据入站人群特定字段的值来限制区段人群。选择要分组的字段，然后指定要使用的值。
   * **[!UICONTROL By data grouping (as a %)]**：您可以使用百分比来根据特定入站人口字段的值来限制区段人群。选择该字段以应用分组，然后指定要使用的值。

      >[!NOTE]
      >
      >可使用各种值的不同限制。For example, you can specify a grouping for the **[!UICONTROL Gender]** field and limit the population with **[!UICONTROL Male]** members to 10 and the population with **[!UICONTROL Female]** members to 30 people. 如果使用多个数据分组字段，则所有分组都必须具有相同的大小。
   ![](assets/wkf_segment_limit_by_grouping.png)

1. 确认区段的配置。
1. 重复执行此过程的步骤到10，根据需要添加多个细分。
1. If necessary, edit the parameters in the **[!UICONTROL Advanced options]** tab:

   * Check the **[!UICONTROL Enable overlapping of outbound populations]** option if you want a member of the inbound population to belong to several segments at the same time. 活动的出站人口可能超过入站人口。
   * Check the **[!UICONTROL Concatenate the code of each segment]** option if the inbound population has already been assigned a segment code that you want to keep. 活动中指定的区段代码将添加到初始区段代码中。
   * Check the **[!UICONTROL Generate complement]** option if you would like to exploit the remaining population.

1. 确认活动的配置并保存工作流。

## Example {#example}

以下示例显示了数据库配置文件根据其年龄组的划分情况。工作流程的目的是为每个年龄组发送一封特定电子邮件。考虑到此工作流程是测试营销活动的一部分，每个细分最多只能包含100个随机选择的配置文件，以便使用受限和代表的受众。

![](assets/wkf_segment_example_4.png)

该工作流由以下元素组成：

* A **[!UICONTROL Scheduler]** activity to specify the workflow's execution date. Refer to the [Scheduler](../../automating/using/scheduler.md) section.
* **[!UICONTROL Query]** 用于定位其生日和电子邮件地址的人员的活动的活动。Refer to the [Query](../../automating/using/query.md) section.
* **[!UICONTROL Segmentation]** 创建分为不同出站过渡的个区段的活动：18-25年旧、26-32年以及32岁以上的档案。区段是根据以下参数定义的：

   ![](assets/wkf_segment_example_3.png)

   * 年龄上的过滤器，用于定义区段的年龄组

      ![](assets/wkf_segment_new_segment.png)

   * A **[!UICONTROL Random sampling]** type limit that is linked to a **[!UICONTROL Maximum size]** limit of 100

      ![](assets/wkf_segment_example_1.png)

* An **[!UICONTROL Email delivery]** activity per segment. Refer to the [Email delivery](../../automating/using/email-delivery.md) section.

