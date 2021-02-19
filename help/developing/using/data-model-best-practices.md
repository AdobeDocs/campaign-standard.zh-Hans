---
solution: Campaign Standard
product: campaign
title: Adobe Campaign Standard中的数据模型最佳实践
description: 了解设计Adobe Campaign Standard数据模型时的最佳实践。
audience: developing
content-type: reference
topic-tags: about-custom-resources
context-tags: cusResource,overview;eventCusResource,overview
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1556'
ht-degree: 1%

---


# 数据模型最佳实践{#data-model-best-practices}

本文档概述设计Adobe Campaign数据模型时的主要建议。


>[!NOTE]
>
>要创建和修改资源以扩展Adobe Campaign预定义的数据模型，请参阅[本节](../../developing/using/key-steps-to-add-a-resource.md)。
>
>可以在[此页](../../developing/using/datamodel-introduction.md)中找到内置资源的数据模型表示形式。

## 概述 {#overview}

Adobe Campaign系统极其灵活，可扩展到初始实现之外。 但是，尽管可能性是无限的，但做出明智决策并建立坚实的基础对于开始设计数据模型至关重要。

此文档提供了常见使用案例和最佳实践，以了解如何正确构建Adobe Campaign工具。

## 数据模型架构{#data-model-architecture}

Adobe Campaign Standard是一款功能强大的跨渠道活动管理系统，可帮助您协调线上和线下战略，创造个性化的客户体验。

### 以客户为中心的方法{#customer-centric-approach}

虽然大多数电子邮件服务提供商都在通过以列表为中心的方法与客户进行通信，但Adobe Campaign依靠关系型数据库来充分利用客户及其属性的更广泛视图。

以客户为中心的方法如下图所示。 灰色的&#x200B;**用户档案**&#x200B;资源表示正在围绕其构建所有内容的主客户表：

![](assets/customer-centric-data-model.png)

此[部分](../../developing/using/datamodel-introduction.md)中显示Adobe Campaign默认数据模型。

<!--You can find a datamodel representation for the out-of-the-box resources [here](../../developing/using/datamodel-introduction.md).-->

<!--### What is a customer? {#customer-definition}

If you have customer data in more than one system, you need to determine which solution will allow you to identify records as one person. This work might require rules, eventually a match and merge processes to determine the primary record. This primary record should be the one sent to Adobe Campaign.

While some of this data cleansing might be performed in Adobe Campaign, the recommendation is to run these processes outside and only import clean data in Adobe Campaign. You should keep Campaign as a marketing solution more than a data cleansing tool.

Be able to provide a primary customer record which will be sent to Adobe Campaign.-->

### Adobe Campaign{#data-for-campaign}的数据

应将哪些数据发送给Adobe Campaign? 确定营销活动所需的数据至关重要。

>[!NOTE]
>
>Adobe Campaign不是data warehouse。 因此，请勿尝试将所有可能的客户及其关联信息导入Adobe Campaign。

要决定Adobe Campaign中是否需要属性，请确定属性是否属于以下类别之一：
* 用于&#x200B;**segmentation**&#x200B;的属性
* 用于&#x200B;**数据管理进程**&#x200B;的属性(例如聚合计算)
* 用于&#x200B;**个性化**&#x200B;的属性
* 用于&#x200B;**报告**&#x200B;的属性(可以根据自定义用户档案数据创建报表)

如果不掉入其中任何一个，您很可能不需要在Adobe Campaign中使用此属性。

### 数据类型 {#data-types}

要确保系统的良好架构和性能，请按照以下最佳做法设置Adobe Campaign中的数据：
* 字符串字段的长度应始终用列来定义。 默认情况下，Adobe Campaign的最大长度为255个字符，但如果您已经知道字段的大小不会超过较短的长度，则Adobe建议将字段保持较短。
* 如果您确定源系统中的字段大小被高估，并且无法达到，则可以将Adobe Campaign比源系统中的字段短。 这可能意味着Adobe Campaign中的字符串更短或整数更小。

## 配置数据结构{#configuring-data-structure}

本节概述了[配置资源的数据结构](../../developing/using/configuring-the-resource-s-data-structure.md)时的最佳实践。

### 标识符{#identifiers}

Adobe Campaign资源具有三个标识符，并且可以添加附加标识符。

下表说明了这些标识符及其用途。

>[!NOTE]
>
>显示名称是通过Adobe Campaign用户界面显示给用户的字段的名称。 技术名称是资源定义中的实际字段名称（和表列名称）。

| 显示名称 | 技术名称 | 说明 | 最佳做法 |
|--- |--- |--- |--- |
|  | PK | <ul><li>PKey是Adobe Campaign表的物理主键。</li><li>此标识符通常对特定Adobe Campaign实例唯一。</li><li>在Adobe Campaign Standard中，此值对最终用户不可见（URL中除外）。</li></ul> | <ul><li>通过[API系统](../../api/using/get-started-apis.md)，可以检索PKey值（它是生成/散列值，而不是物理密钥）。</li><li>除了通过API检索、更新或删除记录外，不建议将其用于其他任何用途。</li></ul> |
| ID | name或internalName | <ul><li>此信息是表中记录的唯一标识符。 此值可以手动更新。</li><li>此标识符在部署到其他Adobe Campaign实例时会保留其值。 它必须具有与生成的值不同的名称，才能通过包导出。</li><li>这不是表的实际主键。</li></ul> | <ul><li>请勿使用空格&quot; &quot;、半列&quot;:&quot;或连字符&quot;-&quot;等特殊字符。</li><li>所有这些字符将替换为下划线&quot;_&quot;（允许的字符）。 例如，“abc-def”和“abc:def”将存储为“abc_def”并互相覆盖。</li></ul> |
| 标签 | 标签 | <ul><li>标签是Adobe Campaign中对象或记录的业务标识符。</li><li>此对象允许使用空格和特殊字符。</li><li>它不保证记录的唯一性。</li></ul> | <ul><li>建议确定对象标签的结构。</li><li>这是最易用的解决方案，用于为Adobe Campaign用户标识记录或对象。</li></ul> |
| ACS ID | acsId | <ul><li>可以生成其他标识符：[ACS ID](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)。</li><li>由于PKey不能在Adobe Campaign用户界面中使用，因此这是一种获得在插入用户档案记录期间生成的唯一值的解决方案。</li><li>仅当在将记录插入Adobe Campaign之前在资源中启用了该选项时，才能自动生成该值。</li></ul> | <ul><li>此UUID可用作合并关键项。</li><li>自动生成的ACS ID不能用作工作流或包定义中的引用。</li><li>此值特定于Adobe Campaign实例。</li></ul> |

### 标识键 {#keys}

在Adobe Campaign中创建的每个资源必须至少有一个唯一的[标识密钥](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)。

<!--Most organizations are importing records from external systems. While the physical key of a resource lies behind the PKey attribute, it is possible to determine a custom key in addition.

This custom key is the actual record primary key in the external system feeding Adobe Campaign.

When an out-of-the-box resource has both an internal auto-generated and an internal custom key, the internal key will be set as a unique index in the physical database table.-->

创建自定义资源时，您有两个选项：

* 自动生成的键和内部自定义键的组合。 如果系统键是复合键或不是整数，则此选项很有意思。 整数在大表中提供更高的性能，并与其他表连接。
* 使用主键作为外部系统主键。 此解决方案通常是首选的，因为它通过不同系统之间的一致密钥简化了数据导入和导出的方法。

不应将标识键用作工作流中的引用。

<!--For more on defining identification keys, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).-->

### 索引 {#indexes}

Adobe Campaign会自动将[index](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes)添加到资源中定义的所有主键和内部键。

* Adobe建议定义其他索引，因为它可以提高性能。
* 但是，不要添加太多索引，因为它们在数据库上使用空间。 许多索引也可能对性能产生负面影响。
* 仔细选择需要定义的索引。

<!--For more on defining indexes, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes).

When you are performing an initial import with very high volumes of data insert in Adobe Campaign database, it is recommended to run that import without custom indexes at first. It will allow to accelerate the insertion process. Once you’ve completed this important import, it is possible to enable the index(es).-->

### 链接 {#links}

[本节](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources)中介绍了定义与其他资源的链接。

* 虽然可以在工作流中加入任何表，但Adobe建议直接在数据结构定义中定义资源之间的公用链接。
* 链接的定义应与表中的实际数据保持一致。 错误的定义可能会影响通过链接检索到的数据，例如意外重复记录。
* 将链接命名与资源名称一致：链接名称应有助于了解远程表的内容。
* 请勿将链接命名为后缀为“id”。 例如，将其命名为“transaction”而不是“transactionId”。

<!--For more on defining links with other resources, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources).-->

## 性能{#performance}

为确保在任何时间都能获得更好的性能，请遵循以下最佳实践。

### 一般建议 {#general-recommendations}

* 避免在查询中使用“CONTAINS”等操作。 如果您知道需要什么并希望筛选对象，请对“EQUAL TO”或其他特定筛选器运算符应用相同的条件。
* 在工作流中构建数据时，避免与非索引字段连接。
* 尝试确保诸如导入和导出等流程在工作时间外完成。
* 确保每日所有活动都有计划，并坚持计划。
* 如果每天有一个或几个进程失败，并且如果强制要求在同一天运行该进程，请确保在启动手动进程时没有运行冲突进程，因为这可能会影响系统性能。
* 确保在导入过程中或执行任何手动过程时，不运行任何每日活动。
* 使用一个或多个引用表，而不是在每行中复制字段。 使用键/值对时，最好选择数字键。
* 短字符串仍可接受。 如果外部系统中已有引用表，则重用引用表将有助于数据与Adobe Campaign的集成。

### 一对多关系{#one-to-many-relationships}

* 数据设计会影响可用性和功能。 如果您设计的数据模型具有许多一对多关系，则用户在应用程序中构建有意义的逻辑将更加困难。 对于非技术营销人员而言，一对多过滤逻辑可能难以正确构建和理解。
* 将所有基本字段放在一个表中是件好事，因为它使用户更容易构建查询。 有时，如果可以避免连接，则在表中重复某些字段也会对性能有好处。
* 某些内置功能将不能引用一对多关系，例如优惠加权公式和投放。

### 大表{#large-tables}

以下是在使用大表和复杂连接设计数据模型时应遵循的一些最佳实践。

* 减少列数，特别是通过识别未使用的列数。
* 通过避免复杂连接（如多个条件和/或多个列上的连接）来优化数据模型关系。
* 对于联接键，请始终使用数字数据而不是字符串。
* 尽可能减少日志保留深度。 如果需要更深入的历史记录，您可以聚合计算和/或处理自定义日志表以存储更大的历史记录。