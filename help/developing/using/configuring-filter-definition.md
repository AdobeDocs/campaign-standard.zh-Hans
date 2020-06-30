---
title: 配置筛选条件定义
description: 发现用于管理大数据集的过滤器功能。
page-status-flag: never-activated
uuid: c9db95fe-e9aa-40f8-9c0a-e74bb21ac14b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
discoiquuid: 993ab2bd-e05f-468e-9ef8-a603761247f8
context-tags: cusResource,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cabe064632c9c2e3de93bc1cff6fa217b4fdf3e6
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 1%

---


# 配置筛选条件定义{#configuring-filter-definition}

在选项卡 **[!UICONTROL Filter definition]** 中，您可以创建高级过滤器，用户在创建复杂查询(如定义受众)时可以直接访问这些。

此步骤不是强制性的，因为您仍然能够通过工作流、受众和REST API填充资源并访问其数据。

![](assets/custom_resource_filter-definition.png)

这些过滤器以预配置规则的形式在查询编辑器中使用。 它们允许您限制获得所需配置所需的步骤数，这对于重复分段尤为有用。

例如，您可以创建一个筛选器，以便选择过去三个月内超过特定金额的所有事务。

为此，您需要扩展资源并定义链接到事务处理表（您之前已创建）的筛选器 **[!UICONTROL Profiles]** ，该筛选器具有一条规则，指明事务处理价格必须大于或等于给定参数，并且事务处理日期必须位于与最近三个月相对应的范围内。

1. 确保创建和发布事务表。 See [Creating or extending the resource](../../developing/using/creating-or-extending-the-resource.md).

   >[!NOTE]
   >
   >此过程使用自定义事务表的示例。 根据您的业务需求进行调整。

1. 在定义与资源中的事务处理表相关的筛 **[!UICONTROL Profiles]** 选器之前，请确保定义指向此表的链接并发布更改。 请参 [阅定义与其他资源的链接](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources)[和更新数据库结构](../../developing/using/updating-the-database-structure.md)。
1. 在新筛 **[!UICONTROL Definition]** 选器定义屏幕的选项卡中，选择事务表。

   ![](assets/custom_resource_filter-definition_example-empty.png)

1. 在窗 **[!UICONTROL Add a rule - Profiles/Transactions]** 口中，将事务表拖放到工作区中。 在显示的下一个窗口中，选择要使用的字段。

   ![](assets/custom_resource_filter-definition_example-field.png)

1. 在窗 **[!UICONTROL Optional parameter settings]** 口 **[!UICONTROL Add a rule - Transactions]** 中，选中 **[!UICONTROL Switch to parameters]** 框。

   在中， **[!UICONTROL Filter conditions]**&#x200B;选择运 **[!UICONTROL Greater than or equal to]** 算符。 在字 **[!UICONTROL Parameters]** 段中，输入名称，然后单击加号以创建新参数。

   ![](assets/custom_resource_filter-definition_example-parameter.png)

1. 确认更改。 此定义与用户以后必须填写的可配置字段相对应，才能执行查询。

   ![](assets/custom_resource_filter-definition_ex_edit-rule.png)

1. 将此规则与另一个规则合并，该规则指定事务处理日期必须在与最近三个月相对应的范围内。

   ![](assets/custom_resource_filter-definition_example.png)

1. 选择显示筛选器的类别。

   ![](assets/custom_resource_filter-definition_category.png)

1. 在筛选 **[!UICONTROL Parameters]** 器定义屏幕的选项卡中，修改说明和标签以向用户明确指示筛选器的主题。 此信息将显示在查询编辑器中。

   ![](assets/custom_resource_filter-definition_parameters.png)

   如果定义多个可配置字段，则可以修改它们在界面中的显示顺序。

1. 保存更改并发布资源。 有关此内容的详细信息，请参 [阅更新数据库结构](../../developing/using/updating-the-database-structure.md) 。

发布资 **[!UICONTROL Profiles]** 源扩展后，用户将在查询编辑器界面的快捷键选项卡下看到 [此过滤器](../../automating/using/editing-queries.md) 。

这样，用户在创建电子邮件时便可轻松定义其受众，以发送给过去三个月中花费超过一定金额的所有客户。

![](assets/custom_resource_filter-definition_email-audience.png)

他们只需在显示的对话框中输入所需的金额，而不是自己进行配置。

![](assets/custom_resource_filter-definition_email-audience_filter.png)

配置过滤器后，您可以使用以下语法从Campaign StandardAPI中使用它：

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/by<customFilterName>?<customFilterparam>=<customFilterValue>`

有关此内容的详细信息，请参阅 [Campaign StandardAPI文档](../../api/using/filtering.md#custom-filters)。
