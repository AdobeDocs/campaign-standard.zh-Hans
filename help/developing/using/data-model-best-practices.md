---
title: Adobe Campaign Standard中的数据模型最佳实践
description: 了解设计Adobe Campaign Standard数据模型时的最佳实践。
audience: developing
content-type: reference
topic-tags: about-custom-resources
context-tags: cusResource,overview;eventCusResource,overview
feature: Data Model
role: Developer
level: Experienced
exl-id: 58d4e02f-3c9a-4e5d-a6aa-fdbcec0d8dda
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1557'
ht-degree: 1%

---

# 数据模型最佳实践{#data-model-best-practices}

本文档概述了设计Adobe Campaign数据模型时的主要建议。


>[!NOTE]
>
>要创建和修改资源以扩展Adobe Campaign预定义的数据模型，请参阅 [本节](../../developing/using/key-steps-to-add-a-resource.md).
>
>您可以在中找到内置资源的数据模型表示形式 [此页面](../../developing/using/datamodel-introduction.md).

## 概述 {#overview}

Adobe Campaign系统非常灵活，可以在初始实施之后扩展。 但是，尽管可能性是无限的，但做出明智决策并奠定坚实的基础来开始设计数据模型至关重要。

本文档提供了常见用例和最佳实践，以了解如何正确构建Adobe Campaign工具。

## 数据模型架构 {#data-model-architecture}

Adobe Campaign Standard是一款功能强大的跨渠道活动管理系统，可帮助您调整线上和线下策略以创建个性化的客户体验。

### 以客户为中心的做法 {#customer-centric-approach}

虽然大多数电子邮件服务提供商都通过以列表为中心的方法与客户通信，但Adobe Campaign依靠关系数据库以更广泛地了解客户及其属性。

此以客户为中心的方法如下图所示。 此 **个人资料** 以灰色显示的资源表示表示要围绕其构建所有内容的主客户表：

![](assets/customer-centric-data-model.png)

Adobe Campaign默认数据模型如以下所示 [部分](../../developing/using/datamodel-introduction.md).

<!--You can find a datamodel representation for the out-of-the-box resources [here](../../developing/using/datamodel-introduction.md).-->

<!--### What is a customer? {#customer-definition}

If you have customer data in more than one system, you need to determine which solution will allow you to identify records as one person. This work might require rules, eventually a match and merge processes to determine the primary record. This primary record should be the one sent to Adobe Campaign.

While some of this data cleansing might be performed in Adobe Campaign, the recommendation is to run these processes outside and only import clean data in Adobe Campaign. You should keep Campaign as a marketing solution more than a data cleansing tool.

Be able to provide a primary customer record which will be sent to Adobe Campaign.-->

### Adobe Campaign的数据 {#data-for-campaign}

应将哪些数据发送到Adobe Campaign？ 确定营销活动所需的数据至关重要。

>[!NOTE]
>
>Adobe Campaign不是数据仓库。 因此，请勿尝试将所有可能的客户及其关联信息导入Adobe Campaign。

要决定是否需要在Adobe Campaign中使用某个属性，请确定它是否属于以下类别之一：
* 用于以下内容的属性 **分段**
* 用于以下内容的属性 **数据管理流程** （例如，聚合计算）
* 用于以下内容的属性 **个性化**
* 用于以下内容的属性 **报告** （可以根据自定义用户档案数据创建报表）

如果不属于上述任何一种，您很可能不会在Adobe Campaign中需要此属性。

### 数据类型 {#data-types}

要确保良好的体系结构和系统性能，请遵循以下最佳实践在Adobe Campaign中设置数据：
* 字符串字段的长度应始终使用列进行定义。 默认情况下，Adobe Campaign中的最大长度为255个字符，但是Adobe建议，如果您已经知道大小不会超过更短的长度，则保持字段更短。
* 如果您确定源系统中的字段大小被高估而无法达到，则可以接受Adobe Campaign中的字段比源系统中的字段更短。 这可能意味着Adobe Campaign中的字符串长度更短，整数更小。

## 配置数据结构 {#configuring-data-structure}

此部分概述了以下情况下的最佳实践 [配置资源的数据结构](../../developing/using/configuring-the-resource-s-data-structure.md).

### 标识符 {#identifiers}

Adobe Campaign资源具有三个标识符，可以添加额外的标识符。

下表描述了这些标识符及其用途。

>[!NOTE]
>
>显示名称是通过Adobe Campaign用户界面向用户显示的字段的名称。 技术名称是资源定义中的实际字段名称（以及表列名）。

| 显示名称 | 技术名称 | 说明 | 最佳实践 |
|--- |--- |--- |--- |
|  | PKey | <ul><li>PKey是Adobe Campaign表的物理主键。</li><li>此标识符通常特定于特定的Adobe Campaign实例。</li><li>在Adobe Campaign Standard中，该值对最终用户不可见（在URL中除外）。</li></ul> | <ul><li>通过 [API系统](../../api/using/get-started-apis.md)，则可以检索PKey值（这是生成/哈希值，而不是物理键）。</li><li>除通过API检索、更新或删除记录外，建议不要将其用于其他目的。</li></ul> |
| ID | name或internalName | <ul><li>此信息是表中记录的唯一标识符。 此值可手动更新。</li><li>当部署在Adobe Campaign的其他实例中时，此标识符保持其值。 其名称必须与生成的值不同，才能通过包导出。</li><li>这不是表的实际主键。</li></ul> | <ul><li>请勿使用空格“ ”、半列“：”或连字符“ — ”等特殊字符。</li><li>所有这些字符都将替换为下划线“_”（允许的字符）。 例如，“abc-def”和“abc：def”将存储为“abc_def”并相互覆盖。</li></ul> |
| 标签 | 标签 | <ul><li>标签是Adobe Campaign中对象或记录的业务标识符。</li><li>此对象允许使用空格和特殊字符。</li><li>它不能保证记录的唯一性。</li></ul> | <ul><li>建议确定对象标签的结构。</li><li>这是用于为Adobe Campaign用户标识记录或对象的最用户友好的解决方案。</li></ul> |
| ACS ID | acsId | <ul><li>可以生成附加标识符： [ACS ID](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).</li><li>由于PKey无法在Adobe Campaign用户界面中使用，因此这是一种解决方案，可用于获取在插入个人资料记录期间生成的唯一值。</li><li>只有在将记录插入Adobe Campaign之前在资源中启用了该选项，才能自动生成该值。</li></ul> | <ul><li>此UUID可用作协调密钥。</li><li>自动生成的ACS ID不能用作工作流或包定义中的引用。</li><li>此值特定于Adobe Campaign实例。</li></ul> |

### 标识键 {#keys}

在Adobe Campaign中创建的每个资源必须至少有一个唯一 [标识键](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).

<!--Most organizations are importing records from external systems. While the physical key of a resource lies behind the PKey attribute, it is possible to determine a custom key in addition.

This custom key is the actual record primary key in the external system feeding Adobe Campaign.

When an out-of-the-box resource has both an internal auto-generated and an internal custom key, the internal key will be set as a unique index in the physical database table.-->

创建自定义资源时，您有两个选项：

* 自动生成的键和内部自定义键的组合。 如果系统键是复合键或不是整数，则此选项很有趣。 整数将在大表中提供更高的性能，并可与其他表连接。
* 使用主键作为外部系统主键。 此解决方案通常是首选的，因为它简化了导入和导出数据的方法，在不同的系统之间使用了一致的密钥。

标识键不应用作工作流中的引用。

<!--For more on defining identification keys, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).-->

### 索引 {#indexes}

Adobe Campaign会自动添加 [索引](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes) 到资源中定义的所有主键和内部键。

* Adobe建议定义其他索引，因为它可能会提高性能。
* 但是，不要添加太多索引，因为它们会占用数据库的空间。 大量索引也可能对性能产生负面影响。
* 仔细选择需要定义的索引。

<!--For more on defining indexes, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes).

When you are performing an initial import with very high volumes of data insert in Adobe Campaign database, it is recommended to run that import without custom indexes at first. It will allow to accelerate the insertion process. Once you’ve completed this important import, it is possible to enable the index(es).-->

### 链接 {#links}

有关定义与其他资源的链接的详情，请参阅 [本节](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources).

* 虽然可以在工作流中连接任何表，但Adobe建议直接在数据结构定义中定义资源之间的通用链接。
* 应根据表中的实际数据来定义链接。 错误定义可能会影响通过链接检索的数据，例如意外地重复记录。
* 使用与资源名称一致的名称命名您的链接：链接名称应该有助于了解远程表是什么。
* 请勿将具有“id”的链接命名为后缀。 例如，将其命名为“transaction”，而不是“transactionId”。

<!--For more on defining links with other resources, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources).-->

## 性能 {#performance}

为了确保随时获得更好的性能，请遵循以下最佳实践。

### 一般建议 {#general-recommendations}

* 避免在查询中使用“CONTAINS”等操作。 如果您知道应该过滤哪些内容，并且希望对其进行过滤，请使用“EQUAL TO”或其他特定的过滤器运算符应用相同的条件。
* 在工作流中构建数据时，避免加入未编制索引的字段。
* 请尝试确保导入和导出等流程在工作时间之外执行。
* 确保所有日常活动都有一个时间表，并遵守时间表。
* 如果有一个或几个每日进程失败，并且如果必须在同一天运行它，请确保在启动手动进程时没有冲突进程在运行，因为这会影响系统性能。
* 确保在导入流程期间或执行任何手动流程时，不会运行任何每日营销活动。
* 使用一个或多个引用表，而不是在每行中复制字段。 使用键/值对时，最好选择数字键。
* 短字符串仍可接受。 如果引用表已在外部系统中，则重用它有助于将数据与Adobe Campaign集成。

### 一对多关系 {#one-to-many-relationships}

* 数据设计会影响可用性和功能。 如果您设计的数据模型具有大量一对多关系，则会使用户更难以在应用程序中构建有意义的逻辑。 对于非技术性营销人员，可能很难正确构建和理解一对多过滤器逻辑。
* 将所有重要字段放在一个表中很好，因为这样用户更容易构建查询。 有时，如果可以避免联接，则跨表复制某些字段对性能也有好处。
* 某些内置功能无法引用一对多关系，例如优惠权重公式和投放。

### 大型表 {#large-tables}

以下是使用大型表和复杂连接设计数据模型时应遵循的一些最佳实践。

* 减少列数，特别是通过标识未使用的列。
* 通过避免复杂连接（如多个条件和/或多个列上的连接）优化数据模型关系。
* 对于联接键，请始终使用数字数据，而不是字符串。
* 尽可能减少日志保留的深度。 如果需要更深入的历史记录，可以聚合计算和/或处理自定义日志表以存储更大的历史记录。
