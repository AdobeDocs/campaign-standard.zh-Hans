---
title: 配置过滤器定义
seo-title: 配置过滤器定义
description: 配置过滤器定义
seo-description: 发现用于管理大型数据集的过滤器功能。
page-status-flag: 从未激活
uuid: c9db95fe-e9 aa-40f8-9c0 a-e74 bb21 ac14 b
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
discoiquuid: 993ab2bd-e05 f-468e-9ef8-a603761247 f8
context-tags: CusResource，main
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Configuring filter definition{#configuring-filter-definition}

**[!UICONTROL Filter definition]** 在选项卡中，您可以创建高级过滤器，用户可在创建复杂查询时直接访问这些过滤器，例如定义受众时。

此步骤不是强制性的，因为您仍能够填充资源并通过工作流程、受众和REST API访问数据。

![](assets/custom_resource_filter-definition.png)

这些过滤器使用预配置规则的形式在查询编辑器中使用。它们允许您限制获取所需配置所需的步骤数，这对于重复的细分尤为有利。

例如，您可以创建一个过滤器，以便在过去三个月内选择大于特定金额的所有事务。

To do this, you need to extend the **[!UICONTROL Profiles]** resource and define a filter linking to a transaction table (that you have previously created) with a rule indicating that the transaction price must be greater than or equal to a given parameter and that the transaction date must fall within a range corresponding to the last three months.

1. 确保创建和发布事务表。See [Creating or extending the resource](../../developing/using/creating-or-extending-the-resource.md).

   >[!NOTE]
   >
   >此过程使用自定义事务表的示例。对于您的案例，请根据您的业务需求进行调整。

1. Before defining a filter related to the transaction table in the **[!UICONTROL Profiles]** resource, make sure you define the link to this table and publish your changes. See [Defining links with other resources](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources) and [Updating the database structure](../../developing/using/updating-the-database-structure.md).
1. In the **[!UICONTROL Definition]** tab of your new filter's definition screen, select the transaction table.

   ![](assets/custom_resource_filter-definition_example-empty.png)

1. In the **[!UICONTROL Add a rule - Profiles/Transactions]** window, drag and drop the transaction table into the workspace. 在显示的下一个窗口中，选择要使用的字段。

   ![](assets/custom_resource_filter-definition_example-field.png)

1. In the **[!UICONTROL Optional parameter settings]** of the **[!UICONTROL Add a rule - Transactions]** window, check the **[!UICONTROL Switch to parameters]** box.

   In the **[!UICONTROL Filter conditions]**, select the **[!UICONTROL Greater than or equal to]** operator. In the **[!UICONTROL Parameters]** field, enter a name and click the plus sign to create the new parameter.

   ![](assets/custom_resource_filter-definition_example-parameter.png)

1. 确认所做的更改。此定义与可配置字段对应，用户必须稍后填写该字段才能执行查询。

   ![](assets/custom_resource_filter-definition_ex_edit-rule.png)

1. 将此规则与另一规则相结合，规定事务日期必须介于与过去三个月对应的范围内。

   ![](assets/custom_resource_filter-definition_example.png)

1. 选择将显示筛选器的类别。

   ![](assets/custom_resource_filter-definition_category.png)

1. In the **[!UICONTROL Parameters]** tab of the filter definition screen, modify the description and the label to clearly indicate the subject of your filter to the users. 此信息将显示在查询编辑器中。

   ![](assets/custom_resource_filter-definition_parameters.png)

   如果定义多个可配置字段，则可以修改它们在界面中显示的顺序。

1. 保存更改并发布资源。For more on this, refer to the [Updating the database structure](../../developing/using/updating-the-database-structure.md) section.

Once the **[!UICONTROL Profiles]** resource extension is published, the users will see this filter under the shortcuts tab in the [query editor](../../automating/using/editing-queries.md) interface.

这将允许用户在创建电子邮件时轻松定义其受众，以发送给过去三个月内支出超过特定金额的所有客户。

![](assets/custom_resource_filter-definition_email-audience.png)

他们只需在显示的对话框中输入所需的数量，而不是自己配置。

![](assets/custom_resource_filter-definition_email-audience_filter.png)

