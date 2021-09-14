---
title: 创建受众
description: 了解如何在 Adobe Campaign 中创建受众。
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: readAudience,main;audience,overview;delivery,audience,back
feature: Audiences
role: User
level: Beginner
exl-id: b40e4f6f-34bb-40f9-80e8-e9f1bce5548c
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '969'
ht-degree: 100%

---

# 创建受众{#creating-audiences}

## 创建查询受众 {#creating-query-audiences}

本节介绍如何创建&#x200B;**查询**&#x200B;受众。您也可以通过导入文件或在[工作流](../../automating/using/get-started-workflows.md)中设置定向以创建受众。

在受众列表中，您可以通过对 Adobe Campaign 用户档案执行查询创建受众，也可通过导入 Adobe Experience Cloud 受众以创建受众。

1. 通过 **[!UICONTROL Audiences]** 选项卡或卡，转到受众列表。

   ![](assets/audiences_query_1.png)

1. 选择 **[!UICONTROL Create]** 以访问用于创建新受众的屏幕。

   ![](assets/audiences_query.png)

1. 为受众命名。受众标签将会用在受众的列表和查询工具的面板中。
1. 选择 **[!UICONTROL Query]** 受众类型：每次重用时重新计算由查询定义的受众。

   ![](assets/audience_type_selection.png)

1. 然后，选择您要用于筛选客户的 **[!UICONTROL Targeting dimension]**。每个受众由单个定向维度组成。例如，不能创建同时包含用户档案、测试用户档案和订阅者的受众。有关定向维度的更多信息，请参阅[此页面](../../automating/using/query.md#targeting-dimensions-and-resources)。
1. 创建查询以定义受众群体。请参阅关于[编辑查询](../../automating/using/editing-queries.md)的章节。
1. 单击 **[!UICONTROL Create]** 按钮以保存受众。

>[!NOTE]
>
>您可以向此受众添加说明，并通过 **[!UICONTROL Edit properties]** 图标定义访问权限。

## 创建列表受众 {#creating-list-audiences}

本节介绍如何在工作流中设置定向后创建&#x200B;**列表**&#x200B;受众。您也可以通过将文件导入[工作流](../../automating/using/get-started-workflows.md)创建受众，或通过 **[!UICONTROL Audiences]** 菜单中的查询创建受众。

要创建&#x200B;**列表**&#x200B;受众，请执行以下步骤：

1. 在“**营销活动**”选项卡中，单击&#x200B;**“创建”**，然后选择&#x200B;**“工作流”**。

   ![](assets/audiences_list_1.png)

1. 拖放，然后配置定向活动，以便您选择具有&#x200B;**已知**&#x200B;维度的群体。可用活动的列表及其配置详情，请参见[定向活动](../../automating/using/about-targeting-activities.md)一节。

   您可以使用 **[!UICONTROL Query]** 活动，或使用 **[!UICONTROL Load file]** 活动导入数据，然后再使用 **[!UICONTROL Reconciliation]** 活动以标识导入数据的维度。在本例中，我们希望通过 **[!UICONTROL Query]** 活动，定向“订阅了体育新闻快讯”的收件人。

   ![](assets/audiences_list_2.png)

1. 定向后，将 **[!UICONTROL Save audience]** 活动拖放到您的工作流中。例如，您可以选择 **[!UICONTROL Create or update an audience]**，以创建受众并使用新数据自动更新。在本例中，请在工作流的开头添加 **[!UICONTROL Scheduler]** 活动。

   有关配置此活动的更多信息，请参阅[保存受众](../../automating/using/save-audience.md)一节。

   ![](assets/audiences_list_3.png)

1. 保存并启动工作流。

   使用已知维度定向后，执行 **[!UICONTROL Save audience]**，通过此活动创建的受众就是&#x200B;**列表**&#x200B;受众。

   随后可通过受众列表访问所保存受众的详情视图，以查看该受众的内容。此视图中可用的列，对应于工作流保存活动集客过渡的列。例如：所导入文件的列、从查询添加的其他数据。

   ![](assets/audiences_list_4.png)

## 创建文件受众 {#creating-file-audiences}

本节详细介绍如何通过将文件导入到&#x200B;**工作流**&#x200B;中来创建文件受众。您也可以通过在[工作流](../../automating/using/get-started-workflows.md)中的定向活动创建受众，或通过 **[!UICONTROL Audiences]** 菜单中的查询创建受众。

要创建&#x200B;**文件**&#x200B;受众，请按照以下步骤进行操作：

1. 在“**营销活动**”选项卡中，单击&#x200B;**“创建”**，然后选择&#x200B;**“工作流”**。
1. 拖放，然后配置 **[!UICONTROL Load file]** 活动，以便在执行工作流时导入包含&#x200B;**未知**&#x200B;维度的群体。有关配置此活动的更多信息，请参阅[加载文件](../../automating/using/load-file.md)一节。

   ![](assets/audience_files_1.png)

1. 执行 **[!UICONTROL Load file]** 活动后，拖放 **[!UICONTROL Save audience]** 活动。有关配置此活动的更多信息，请参阅[保存受众](../../automating/using/save-audience.md)一节。
1. 保存并启动工作流。

   ![](assets/audience_files_2.png)

   导入后，执行 **[!UICONTROL Save audience]**，其数据维度为未知，通过此活动创建的受众就是&#x200B;**文件**&#x200B;受众。

   随后可通过受众列表访问所保存受众的详情视图，以查看该受众的内容。此视图中可用的列，对应于工作流保存活动集客过渡的列。例如：所导入文件的列、从查询添加的其他数据。

   ![](assets/audience_files_3.png)

## 创建 Experience Cloud 受众 {#creating-experience-cloud-audiences}

Adobe Campaign 允许您使用 Adobe Experience Cloud 共享和交换受众。**Experience Cloud** 类型的受众，可通过 **[!UICONTROL Import shared audience]** 工作流，直接从 People 核心服务导入到 Adobe Campaign。

与从 Adobe Campaign 查询用户档案的&#x200B;**查询**&#x200B;类型受众不同，**Experience Cloud** 受众由一系列“访客 ID”组成。

要使此集成正常工作，您首先需要对其进行配置。有关配置以及如何通过 People 核心服务导入或导出受众的更多信息，请参阅以下[章节](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md)。

![](assets/audience_peoplecore.png)

## 编辑受众 {#editing-audiences}

受众有不同的编辑方式，具体方式取决于受众类型，如下所示：

* 要编辑&#x200B;**查询**，请通过 **[!UICONTROL Audiences]** 菜单转到受众列表，或从 Adobe Campaign 主页转到 **[!UICONTROL Audiences]** 卡。

   打开相关受众。可对以前创建受众的所有元素进行编辑。

   >[!CAUTION]
   >
   >如果更改查询中的 **[!UICONTROL Filtering dimension]** 规则，则之前已定义的规则将丢失。

* 要编辑&#x200B;**列表**&#x200B;或&#x200B;**文件**&#x200B;受众，请编辑创建该受众的工作流，并修改 **[!UICONTROL Save audience]** 活动。启动工作流，以便修改受众。
* 要编辑 **Experience Cloud** 受众，请参阅[通过 People 核心服务导入/导出受众](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md)一节。

## 删除受众 {#deleting-audiences}

有两种方法可删除一个或多个受众。首先，为受众添加截止日期

为实现此操作，请执行以下步骤：

1. 访问其中一个受众。
1. 单击 ![](assets/edit_darkgrey-24px.png) 按钮以访问该受众的配置。

   ![](assets/audience_delete_2.png)

1. 在 **[!UICONTROL Expires on]** 字段中，为该受众添加截止日期。

   ![](assets/audience_delete_3.png)

1. 单击 **[!UICONTROL Confirm]**，然后单击 **[!UICONTROL Save]**。

截止日期配置完成。一旦达到此日期，该受众将自动删除。

还有另一种删除受众的方法，您只需选择一个或多个受众，然后单击 **[!UICONTROL Delete element]** 按钮即可。

![](assets/audience_delete_1.png)
