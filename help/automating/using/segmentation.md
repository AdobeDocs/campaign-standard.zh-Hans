---
title: 分段
description: 使用分段活动，您可以根据由之前放在工作流中的活动计算的客户群创建一个或多个区段。
page-status-flag: never-activated
uuid: 77796f18-cad5-4e7a-9d7b-4ed0dd8943bf
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 0ccd9d02-772e-406b-874a-5381dd0c8709
context-tags: segmentation,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 740de9fe4666bf12fc97cfa434414668d9394504
workflow-type: tm+mt
source-wordcount: '993'
ht-degree: 0%

---


# 分段{#segmentation}

## 说明 {#description}

![](assets/segmentation.png)

通过 **[!UICONTROL Segmentation]** 活动，您可以根据活动在工作流中放置的先前计算的群体创建一个或多个区段。 在活动结束时，可以在一个过渡或不同过渡中处理这些数据。

>[!NOTE]
>
>默认情况下，入站人口的成员只能属于一个区段。 过滤器根据活动中段的顺序应用。

## 使用环境 {#context-of-use}

活动 **[!UICONTROL Segmentation]** 通常位于定位活动之后(查询、交叉点、合并、排除等) 以定义基于其形成分段的标准种群。

## Configuration {#configuration}

1. 将活动拖放 **[!UICONTROL Segmentation]** 到工作流中。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮打开它。
1. 在选 **[!UICONTROL General]** 项卡中，选 **[!UICONTROL Resource type]** 择要执行分段的位置：

   * **[!UICONTROL Database resource]** 如果对数据库中已存在的数据执行分段。 根据 **[!UICONTROL Filtering dimension]** 要细分的数据选择数据。 默认情况下，对用户档案执行分 **段**。
   * **[!UICONTROL Temporary resource]** 如果对工作流的临时数据执行分段： 选择包 **[!UICONTROL Targeted set]** 含要区段的数据。 在导入文件或数据库中的数据已丰富时，可以遇到此用例。

1. 选择要使用的出站过渡类型：

   * **[!UICONTROL Generate one transition per segment]**: 在过渡结束时，会为每个已配置的区段添加一个出站活动。
   * **[!UICONTROL Generate all segments in one transition]**: 所有已配置的区段都重新分组为一个出站过渡。 指定过渡标签。 每个区段的成员会保留分配给它们的段代码。

1. 使用或按钮添加 ![](assets/add_darkgrey-24px.png) 区段 **[!UICONTROL Add an element]** 并指定标准属性：

   * **[!UICONTROL Do not activate the transition if the population is empty]**: 只有在检索数据时，才会启用段。
   * **[!UICONTROL Filter initial population (query)]**: 允许您过滤此区段的人口。
   * **[!UICONTROL Limit segment population]**: 允许您限制区段大小。
   * **[!UICONTROL Filter and limit segment population]**: 允许您过滤区段填充并限制其大小。
   * **[!UICONTROL Label]**: 区段标签。
   * **[!UICONTROL Segment code]**: 分配给区段填充的代码。段代码可以使用标准表达式和事件变量进行个性化(请参 [阅使用事件变量自定义活动](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables))。
   * **[!UICONTROL Exclude segment from population]**: 允许您从活动的出站人口中排除指定的区段。 此选项仅在选中时 **[!UICONTROL Generate all segments in the same transition]** 才可用。
   ![](assets/wkf_segment_new_segment.png)

1. 打开区段的详细视图以访问后者的配置选项。 为此，请选中活动区段列表中的相关框，然后选择 ![](assets/wkf_segment_parameters_24px.png)。
1. 如果选中了筛选初始填充的选项，请打开选 **[!UICONTROL Filter]** 项卡并指定区段的填充。 过滤器基于步骤4中选择的过滤维度。 有关人口筛 [选的更多信息](../../automating/using/editing-queries.md) ，请参阅查询编辑部分。

   如果对临时资源进行分段，则此选项卡中不提供人口的计数和预览。

1. 如果选中了限制段大小的选项，请打开选 **[!UICONTROL Limitation]** 项卡。

   首先，选 **[!UICONTROL Type of limit]** 择要使用的：

   * **[!UICONTROL Random sampling]**: 根据需要，会随机选择区段填充，并考 **[!UICONTROL Filter]** 虑选项卡的配置。
   * **[!UICONTROL Ordered sampling]**: 按顺序选择区段填充。 因此，必须指定要考虑的列和应用的排序类型。 例如，如果在应用时 **选择** “年龄”字段作为排序列， **[!UICONTROL Descending sort]** 并将限制设置为100，则只保留前100名最年长的人的用户档案。
   现在，指定 **[!UICONTROL Limit]** 区段的大小：

   * **[!UICONTROL Size (as a % of the initial population)]**: 使用活动初始人口的百分比指定区段大小。
   * **[!UICONTROL Maximum size]**: 为区段填充指定最大成员数。
   * **[!UICONTROL By data grouping]**: 您可以根据入站人口的特定字段的值限制段人口。 选择要分组的字段，然后指定要使用的值。
   * **[!UICONTROL By data grouping (as a %)]**: 您可以使用百分比，根据特定入站人口字段的值限制区段人口。 选择要应用分组的字段，然后指定要使用的值。

      >[!NOTE]
      >
      >可以对每个值使用不同的限制。 例如，您可以为字段指定分组， **[!UICONTROL Gender]** 并将具有成员的 **[!UICONTROL Male]** 人口限制为10，具有成员 **[!UICONTROL Female]** 的人口限制为30。 如果您使用多个数据分组字段，则所有分组必须具有相同的大小。
   ![](assets/wkf_segment_limit_by_grouping.png)

1. 确认区段的配置。
1. 重复此过程的步骤6到10，根据需要添加任意数量的段。
1. 如有必要，请编辑选项卡中的 **[!UICONTROL Advanced options]** 参数：

   * 如果 **[!UICONTROL Enable overlapping of outbound populations]** 希望入站人口的成员同时属于多个区段，请选中此选项。 活动的出站人口可能超过入站人口。
   * 如果 **[!UICONTROL Concatenate the code of each segment]** 已为入站人口分配要保留的段代码，请选中此选项。 在活动中指定的段代码将添加到初始段代码。
   * 如果要 **[!UICONTROL Generate complement]** 利用剩余人口，请选中此选项。

1. 确认活动的配置并保存工作流。

## Example {#example}

以下示例显示了根据用户档案组对数据库数据进行细分。 该工作流旨在为每个年龄组发送特定电子邮件。 考虑到此工作流是测试活动的一部分，每个用户档案段最多只能包含100个随机选择的受众，以便同时使用受限且具有代表性的。

![](assets/wkf_segment_example_4.png)

工作流由以下元素组成：

* 用 **[!UICONTROL Scheduler]** 于指定工作流执行日期的活动。 请参阅 [调度程序](../../automating/using/scheduler.md) 部分。
* 向已 **[!UICONTROL Query]** 输入生日和电子邮件地址的目标用户档案的活动。 请参阅 [查询](../../automating/using/query.md) 部分。
* 用于 **[!UICONTROL Segmentation]** 创建3个区段的活动，这些区段分为不同的出站过渡: 18-25岁，26-32岁，用户档案32岁以上。 段根据以下参数进行定义：

   ![](assets/wkf_segment_example_3.png)

   * 用于定义区段年龄组的年龄过滤器

      ![](assets/wkf_segment_new_segment.png)

   * 链 **[!UICONTROL Random sampling]** 接到限制为100的类 **[!UICONTROL Maximum size]** 型限制

      ![](assets/wkf_segment_example_1.png)

* 每个 **[!UICONTROL Email delivery]** 区段的活动。 请参阅“电子邮 [件投放](../../automating/using/email-delivery.md) ”部分。

