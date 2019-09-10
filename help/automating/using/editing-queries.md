---
title: 编辑查询
seo-title: 编辑查询
description: 编辑查询
seo-description: 借助预定义的过滤器和规则构建人群。
page-status-flag: 从未激活
uuid: a49c7739-a96 c-45cb-9ac5-1ce299161 a97
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 筛选数据
discoiquuid: 84306a1e-0d9f-44cc-88a7-36d7e5b4da1f
context-tags: queryFilter，概述；受众，主要
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: bb65cbf808a95e8b42b2a682b7c0a9cc6225d920

---


# 编辑查询{#editing-queries}

## 关于查询编辑器 {#about-query-editor}

查询编辑器是一个向导，用于过滤Adobe Campaign数据库中包含的数据。

通过此功能，您可以通过预定义的过滤器和规则来构建用户以更好地定位收件人。

一些应用程序功能使用它来：

* 创建 **查询** 类型 **受众**
* 定义 **电子邮件** 目标
* 定义 **工作流** 活动中的人群

## 查询编辑器界面 {#query-editor-interface}

查询编辑器由 **调色板** 和 **工作区**&#x200B;组成。

![](assets/query_editor_overview.png)

### 调色板 {#palette}

调色板位于编辑器左侧，分为两个选项卡，它们包含划分为主题块的元素。这些选项卡有：

* **快捷键**、默认情况下可用或由实例管理员创建的快捷键。您可以在此处找到字段、节点、分组、1-1链接、1-N链接和其他预定义筛选器。
* **用于** 访问目标资源中所有可用字段的资源管理器：节点，分组元素，链接(1-1和1-N)。

必须将选项卡中包含的元素移入工作区，以便进行配置并考虑查询。根据选择的定位维度(请参阅 [定位维度和资源](../../automating/using/query.md#targeting-dimensions-and-resources))，您可以：

* 逐个选择受众或档案
* 使用预定义滤镜
* 为您选择的字段定义简单规则
* 定义允许您将函数应用于特定字段的高级规则

### Workspace {#workspace}

工作区是中心区域，您可以在该区域中配置和合并规则、受众以及从调色板中添加的预定义筛选器。

当您将元素从调色板移到工作区时，将打开一个新窗口，您可以开始 [创建查询](../../automating/using/editing-queries.md#creating-queries)。

## 创建查询 {#creating-queries}

查询编辑器可用于定义消息中的受众或测试配置文件、工作流中的人群以及创建查询类型受众。

创建工作流时，可以 **[!UICONTROL Audience]** 在窗口中创建分发或 **在查询** 活动中定义查询。

1. 将元素从调色板移至工作区。此时将打开编辑规则的窗口。

   * 对于字符串或数值 **字段**，指定比较运算符和值。

      ![](assets/query_editor_audience_definition2.png)

   * 对于日期、日期和时间 **字段**，您可以选择定义特定日期、两个日期之间的范围或相对于查询执行日期的句点。

      ![](assets/query_editor_date_field.png)

   * 对于Boolean **字段**，选中链接到可能的字段值的框。
   * 对于 **分组** 字段，选择要在其上创建规则的分组字段，然后以与其他字段相同的方式定义条件。

      ![](assets/query_editor_audience_definition4.png)

   * 对于具有其他数据库资源的 **1-1** 链接，请直接从目标中选择一个值。

      ![](assets/query_editor_audience_definition5.png)

   * 对于 **具有其他数据库资源的1-N** 链接，您可以在第二个资源的字段中定义子查询。

      您无需指定子条件。

      例如，只能在配置文件跟踪日志上选择 **[!UICONTROL Exists]** 操作符并批准规则。该规则将返回跟踪日志存在的所有配置文件。

      ![](assets/query_editor_audience_definition6.png)

   * 对于 **预定义的过滤器**，根据提供的条件输入或选择您喜欢的元素。

      管理员可以创建过滤器以促进复杂和重复的查询。它们将以预配置规则的形式显示在查询编辑器中，并限制用户执行的步骤数。

      ![](assets/query-editor_filter_email-audience_filter.png)

1. 您可以指定规则的名称。然后，它将显示为工作区中的规则名称。如果未提供规则，则会自动显示条件的自动描述。
1. 要组合工作区元素，请将它们彼此锁定以创建不同的组和/或组级别。然后，您可以选择一个逻辑运算符，将元素组合到同一级别：

   * **[!UICONTROL AND]**：两个条件的交叉点。只考虑与每个标准匹配的元素。
   * **[!UICONTROL OR]**：两个条件的联合。考虑到至少两个条件之一的元素被考虑在内。
   * **[!UICONTROL EXCEPT]**：排除条件。与第一个标准匹配的元素会被考虑在内，除非它们也符合第二个标准。

1. 您现在可以使用操作栏中 ![](assets/count.png) 的和 ![](assets/preview.png) 按钮来计算和预览查询目标的元素数。

   ![](assets/query_editor_combining_rules.png)

如果要修改查询的元素，请单击编辑图标。规则将在之前配置时打开，然后您可以执行必要的调整。

您的查询现已创建并定义，这使您能够建立一个人群以更好地个性化您的交付。

**相关主题：**

* [高级函数](../../automating/using/advanced-expression-editing.md)
* [定义过滤器](../../developing/using/configuring-filter-definition.md)
* [使用案例：创建一次每周一次的电子邮件分发](../../automating/using/workflow-weekly-offer.md)
* [使用案例：在位置上创建分发分段](../../automating/using/workflow-segmentation-location.md)
* [使用案例：通过补充创建交付](../../automating/using/workflow-created-query-with-complement.md)
* [使用案例：重定向向非Opener发送新交付的工作流](../../automating/using/workflow-cross-channel-retargeting.md)
