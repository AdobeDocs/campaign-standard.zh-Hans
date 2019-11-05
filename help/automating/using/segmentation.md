---
title: 分段
description: “分段”活动允许您根据工作流中先前放置的活动计算的人群创建一个或多个区段。
page-status-flag: 从未激活
uuid: 77796f18-cad5-4e7a-9d7b-4ed0dd8943bf
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 自动化
content-type: 参考
topic-tags: 定位活动
discoiquuid: 0ccd9d02-772e-406b-874a-5381dd0c8709
context-tags: 分段，主
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 分段{#segmentation}

## 说明 {#description}

![](assets/segmentation.png)

通过 **[!UICONTROL Segmentation]** 活动，您可以根据工作流中先前放置的活动计算的人口来创建一个或多个区段。 在活动结束时，可以在一个过渡或不同的过渡中处理这些过渡。

>[!NOTE]
>
>默认情况下，入站人群的成员只能属于一个区段。 根据活动中区段的顺序应用过滤器。

## 使用环境 {#context-of-use}

活 **[!UICONTROL Segmentation]** 动通常位于定位活动（查询、交叉、联合、排除等）之后以定义基于其形成段的标准种群。

## 配置 {#configuration}

1. 将活动拖放 **[!UICONTROL Segmentation]** 到工作流中。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮将其打开。
1. 选择 **[!UICONTROL Resource type]** 要执行分段的位置：

   * **[!UICONTROL Database resource]** 如果对数据库中已存在的数据执行分段。 根据 **[!UICONTROL Filtering dimension]** 要细分的数据选择。 默认情况下，会对配置文件执行 **分段**。
   * **[!UICONTROL Temporary resource]** 如果对工作流的临时数据执行分段：选择包 **[!UICONTROL Targeted set]** 含要细分的数据的内容。 在导入文件或数据库中的数据已丰富时，可以遇到此用例。

1. 选择要使用的出站过渡类型：

   * **[!UICONTROL Generate one transition per segment]**:在活动结束时，将为每个已配置的区段添加一个出站过渡。
   * **[!UICONTROL Generate all segments in one transition]**:所有已配置的区段将重新分组为一个出站过渡。 指定过渡标签。 每个区段的成员会保留已分配给它们的区段代码。

1. 使用或按钮添加区 ![](assets/add_darkgrey-24px.png) 段并 **[!UICONTROL Add an element]** 指定标准属性：

   * **[!UICONTROL Do not activate the transition if the population is empty]**:只有检索数据时，才会启用区段。
   * **[!UICONTROL Filter initial population (query)]**:允许您过滤此区段的人群。
   * **[!UICONTROL Limit segment population]**:允许您限制区段大小。
   * **[!UICONTROL Filter and limit segment population]**:允许您过滤区段群并限制其大小。
   * **[!UICONTROL Label]**:区段标签。
   * **[!UICONTROL Segment code]**:分配给区段填充的代码。区段代码可以使用标准表达式和事件变量进行个性化设置(请参阅使用 [事件变量自定义活动](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables))。
   * **[!UICONTROL Exclude segment from population]**:允许您从活动的出站人口中排除指定的区段。 此选项仅在选中时才 **[!UICONTROL Generate all segments in the same transition]** 可使用。
   ![](assets/wkf_segment_new_segment.png)

1. 打开区段的详细信息视图以访问后者的配置选项。 为此，请选中活动区段列表中的相关框，然后选择 ![](assets/wkf_segment_parameters_24px.png)。
1. 如果选中了过滤初始人口的选项，请打开选 **[!UICONTROL Filter]** 项卡并指定区段的人口。 过滤器基于在步骤4中选择的过滤维度。 有关人口筛 [选的更多信息](../../automating/using/editing-queries.md) ，请参阅查询编辑部分。

   如果对临时资源执行分段，则此选项卡中不提供人口计数和预览。

1. 如果选中了限制区段大小的选项，请打开选 **[!UICONTROL Limitation]** 项卡。

   首先，选 **[!UICONTROL Type of limit]** 择要使用的：

   * **[!UICONTROL Random sampling]**:根据需要，会随机选择区段群组，并考虑 **[!UICONTROL Filter]** 选项卡的配置。
   * **[!UICONTROL Ordered sampling]**:区段人口按顺序选择。 因此，必须指定要考虑的列和应用的排序类型。 例如，如果在应用时选择“年龄 ******[!UICONTROL Descending sort]** ”字段作为排序列，并将其限制为100，则只保留前100名最年长的人的配置文件。
   现在，指定区 **[!UICONTROL Limit]** 段的大小：

   * **[!UICONTROL Size (as a % of the initial population)]**:使用活动初始人口的百分比指定区段大小。
   * **[!UICONTROL Maximum size]**:为区段人口指定最大成员数。
   * **[!UICONTROL By data grouping]**:您可以根据入站人口的特定字段的值限制区段人口。 选择要分组的字段，然后指定要使用的值。
   * **[!UICONTROL By data grouping (as a %)]**:您可以使用百分比，根据特定入站人口字段的值限制区段人口。 选择要应用分组的字段，然后指定要使用的值。

      >[!NOTE]
      >
      >可以对每个值使用不同的限制。 例如，您可以为字段指定分组， **[!UICONTROL Gender]** 并将具有成员的人 **[!UICONTROL Male]** 口限制为10，将具有成员的人口限制 **[!UICONTROL Female]** 为30人。 如果您使用多个数据分组字段，则所有分组必须具有相同的大小。
   ![](assets/wkf_segment_limit_by_grouping.png)

1. 确认区段的配置。
1. 重复此过程的步骤6到10，根据需要添加任意数量的区段。
1. 如有必要，请编辑选项卡中的 **[!UICONTROL Advanced options]** 参数：

   * 如果 **[!UICONTROL Enable overlapping of outbound populations]** 希望入站人口的成员同时属于多个区段，请选中此选项。 活动的出站人口可能超过入站人口。
   * 如果 **[!UICONTROL Concatenate the code of each segment]** 已为入站人口分配了要保留的区段代码，请选中此选项。 活动中指定的区段代码将添加到初始区段代码。
   * 如果要 **[!UICONTROL Generate complement]** 利用剩余人口，请选中此选项。

1. 确认活动的配置并保存工作流。

## Example {#example}

以下示例显示了根据数据库配置文件的年龄组对其进行细分。 该工作流旨在为每个年龄组发送特定电子邮件。 考虑到此工作流是测试营销活动的一部分，每个区段最多只能包含100个随机选择的配置文件，以便同时使用受限且具有代表性的受众。

![](assets/wkf_segment_example_4.png)

该工作流由以下元素组成：

* 用于 **[!UICONTROL Scheduler]** 指定工作流执行日期的活动。 请参阅“ [Scheduler](../../automating/using/scheduler.md) ”部分。
* 用于 **[!UICONTROL Query]** 定位已输入生日和电子邮件地址的人员的配置文件的活动。 请参阅“ [查询](../../automating/using/query.md) ”部分。
* 用于 **[!UICONTROL Segmentation]** 创建3个细分为不同出站过渡的区段的活动：18-25岁，26-32岁，32岁以上。 区段根据以下参数定义：

   ![](assets/wkf_segment_example_3.png)

   * 用于定义区段年龄组的年龄过滤器

      ![](assets/wkf_segment_new_segment.png)

   * 链 **[!UICONTROL Random sampling]** 接到限制为100的类 **[!UICONTROL Maximum size]** 型限制

      ![](assets/wkf_segment_example_1.png)

* 每个 **[!UICONTROL Email delivery]** 区段的活动。 请参阅电子邮 [件分发](../../automating/using/email-delivery.md) 。

