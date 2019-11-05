---
title: 创建受众
description: 了解如何在Adobe Campaign中创建受众。
page-status-flag: 从未激活
uuid: fe99b31b-a949-4832-b0e6-2b36d1c8be80
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: 参考
topic-tags: 管理受众
discoiquuid: df8bdcfb-be5e-4044-bc26-aa3466accbbe
context-tags: readAudience,main;audience，概述；交付，audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 创建受众{#creating-audiences}

## 创建查询受众 {#creating-query-audiences}

本节介绍如何创建查 **询受众** 。 您还可以通过在工作流中导入文件或定位来创建 [受众](../../automating/using/discovering-workflows.md)。

从受众列表中，您可以通过对Adobe Campaign配置文件执行查询或导入Adobe Experience cloud受众来创建受众。

1. 通过选项卡或卡片转到受 **[!UICONTROL Audiences]** 众列表。

   ![](assets/audiences_query_1.png)

1. 选择 **[!UICONTROL Create]** 以访问屏幕以创建新受众。

   ![](assets/audiences_query.png)

1. 命名受众。 受众标签用于受众列表和查询工具的调色板中。
1. 选择受 **[!UICONTROL Query]** 众类型：在每次进一步使用时，由查询定义的受众被重新计算。

   ![](assets/audience_type_selection.png)

1. 然后，选 **[!UICONTROL Targeting dimension]** 择要用于筛选客户的选项。 每个受众由单个定位维度组成。 例如，您不能创建由档案、测试档案和订阅者组成的受众。 For more on targeting dimensions, refer to [this page](../../automating/using/query.md#targeting-dimensions-and-resources).
1. 创建查询以定义受众群体。 请参阅有关编辑查询 [的部分](../../automating/using/editing-queries.md)。
1. 单击该 **[!UICONTROL Create]** 按钮以保存受众。

>[!NOTE]
>
>您可以向此受众添加描述，并通过图标定义访问 **[!UICONTROL Edit properties]** 授权。

## 创建列表受众 {#creating-list-audiences}

本节介绍如何在工作流中定 **位** ，之后创建List受众。 您还可以通过将文件导入工作流或通过菜 [单中的查询](../../automating/using/discovering-workflows.md) ，来创建受 **[!UICONTROL Audiences]** 众。

要创建 **List受众** ，步骤如下：

1. 在“营销活 **动** ”选项卡中，单击 **创建** ，然后选择 **工作流**。

   ![](assets/audiences_list_1.png)

1. 拖放，然后配置定位活动，以便您选择具有已知维度的 **人群** 。 “定位”活动部分详细介绍了可用活动及其 [配置的列表](../../automating/using/about-targeting-activities.md) 。

   您可以使用活 **[!UICONTROL Query]** 动，或使用活动导入数据， **[!UICONTROL Load file]** 然后使用活动 **[!UICONTROL Reconciliation]** 标识导入的数据的维度。 在此，我们要定位订阅了具有活动的体育新闻快讯的收 **[!UICONTROL Query]** 件人。

   ![](assets/audiences_list_2.png)

1. 定位后，将活动拖放到 **[!UICONTROL Save audience]** 工作流中。 例如，您可以选择创建 **[!UICONTROL Create or update an audience]**&#x200B;受众，然后使用新数据自动更新受众。 在这种情况下，请在工作 **[!UICONTROL Scheduler]** 流程的开头添加活动。

   有关配置此活动的详细信息，请参阅保 [存受众](../../automating/using/save-audience.md) 。

   ![](assets/audiences_list_3.png)

1. 保存并启动工作流。

   由于将 **[!UICONTROL Save audience]** 放在具有已知维度的定位之后，通过此活动创建的受众是列 **表受众** 。

   然后，保存的受众的内容会显示在受众的详细视图中，该视图可通过受众列表访问。 此视图中可用的列与工作流保存活动的入站过渡的列相对应。 例如：导入的文件的列，从查询添加的其他数据。

   ![](assets/audiences_list_4.png)

## 创建文件受众 {#creating-file-audiences}

本节详细介绍如何将文件导 **入工作流** ，从而创建文件受众。 您还可以通过工作流中的定位活动或 [通过菜单](../../automating/using/discovering-workflows.md) 中的查询创建受 **[!UICONTROL Audiences]** 众。

要创建文 **件受众** ，步骤如下：

1. 在“营销活 **动** ”选项卡中，单击 **创建** ，然后选择 **工作流**。
1. 拖放，然后配置一个 **[!UICONTROL Load file]** 活动，该活动允许您在执行工作流时导入具有 **未知维** 的人群。 有关配置此活动的详细信息，请参阅“加 [载文件](../../automating/using/load-file.md) ”部分。

   ![](assets/audience_files_1.png)

1. 在活动后拖 **[!UICONTROL Save audience]** 放活 **[!UICONTROL Load file]** 动。 有关配置此活动的详细信息，请参阅保 [存受众](../../automating/using/save-audience.md) 。
1. 保存并启动工作流。

   ![](assets/audience_files_2.png)

   由于在导 **[!UICONTROL Save audience]** 入后放置数据维度未知，因此通过此活动创建的受众是文件 **受众** 。

   然后，保存的受众的内容会显示在受众的详细视图中，该视图可通过受众列表访问。 此视图中可用的列与工作流保存活动的入站过渡的列相对应。 例如：导入文件的列，从查询添加的其他数据。

   ![](assets/audience_files_3.png)

## 创建Experience cloud受众 {#creating-experience-cloud-audiences}

Adobe Campaign允许您使用Adobe Experience cloud共享和交换受众。 Experience Cloud **type受众可通过技术工作流程从People核心服务直接导入到Adobe Campaign****[!UICONTROL Import shared audience]** 中。

与将 **从Adobe Campaign查询配置文件的查询类型受众不同，** Experience Cloud **** Audience由访客ID列表组成。

要使此集成正常工作，您首先需要配置它。 有关配置以及如何通过“人员”核心服务导入或导出受众的详细信息，请参阅以下 [部分](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md)。

![](assets/audience_peoplecore.png)

## 编辑受众 {#editing-audiences}

根据受众类型，有不同的编辑受众的方法：

* 要编辑 **Query受众** ，请通过菜单或Adobe Campaign主页中 **[!UICONTROL Audiences]** 的卡片转 **[!UICONTROL Audiences]** 到受众列表。

   打开相关受众。 可以编辑先前创建的受众的所有元素。

   >[!CAUTION]
   >
   >如果更改 **[!UICONTROL Filtering dimension]** 查询中的规则，则之前已定义的规则将丢失。

* 要编辑 **List** 或 **File受众，请编辑从中创建该受众的工作流并修改****[!UICONTROL Save audience]** 活动。 启动工作流，以便修改受众。
* 要编辑 **Experience Cloud受众** ，请参阅“使用人员 [核心服务导入／导出受众](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md) ”部分。

## 删除受众 {#deleting-audiences}

有两种方法可删除一个或多个受众。 首先，您可以向受众添加到期日期

为此，请执行以下操作：

1. 访问您的受众之一。
1. 单击 ![](assets/edit_darkgrey-24px.png) 按钮以访问受众的配置。

   ![](assets/audience_delete_2.png)

1. 在字段 **[!UICONTROL Expires on]** 中，为受众添加到期日期。

   ![](assets/audience_delete_3.png)

1. 然后， **[!UICONTROL Confirm]** 单击 **[!UICONTROL Save]**。

您的过期日期现已配置。 一旦到达此日期，您的受众将被自动删除。

或者，如果需要删除受众，您只需选择一个或多个受众，然后单击该按 **[!UICONTROL Delete element]** 钮。

![](assets/audience_delete_1.png)

