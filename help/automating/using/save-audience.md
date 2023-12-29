---
title: 保存受众
description: 利用保存受众活动，可使用工作流上游计算的群体更新现有受众或创建新受众。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: saveAudience,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: c3f029d7-779e-47e7-a925-1e8f672da4dd
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 99%

---

# 保存受众{#save-audience}

## 说明 {#description}

![](assets/save_audience.png)

利用 **[!UICONTROL Save audience]** 活动，可使用工作流上游计算的群体更新现有受众或创建新受众。从此活动创建或更新的受众属于 **List** 或 **File** 受众。这些受众将添加到应用程序受众的列表，并可通过菜单 **[!UICONTROL Audiences]** 使用。

>[!NOTE]
>
>如果通过 **[!UICONTROL Save audience]** 活动创建的受众，已经通过附加数据进行了扩充，您将无法使用这些数据来个性化独立投放。它们只能用于工作流中执行的投放。

利用此活动，还可将用户档案导出为 Adobe Experience Cloud 受众/区段。这样，您就可以在其他 Adobe Experience Cloud 解决方案中利用这些受众。有关共享受众的详细信息，请参阅[使用 Campaign 和 People Core Service](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)。

## 使用环境 {#context-of-use}

**[!UICONTROL Save audience]** 活动主要用于通过将同一工作流中计算得出的群体组转换为可重复利用的受众，将其保留下来。

## 配置 {#configuration}

1. 将 **[!UICONTROL Save audience]** 活动拖放到工作流中。
1. 将其连接到其他定向活动之后，例如查询、交集、并集或排除等等。
1. 选择活动，然后使用所显示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按钮将其打开。
1. 选择要执行的操作：

   * **[!UICONTROL Update an existing audience]**：选择现有受众，然后选择更新类型：

      * **[!UICONTROL Replace audience content with new data]**：替换整个受众内容。旧数据会丢失。只保留来自保存受众活动之集客过渡的数据。
      * **[!UICONTROL Complete audience with new data]**：保留旧受众数据，并将来自保存受众活动之集客过渡的数据添加到旧数据中。

   * **[!UICONTROL Create then update an audience]**：输入受众的名称并选择更新类型。如果受众不存在，则创建受众。如果受众已存在，则会根据选定的模式更新受众：

      * **[!UICONTROL Replace audience content with new data]**：替换整个受众内容。旧数据会丢失。只保留来自保存受众活动之集客过渡的数据。

        警告，此选项会清除更新受众的受众类型和定向维度。

      * **[!UICONTROL Complete audience with new data]**：保留旧受众数据，并将来自保存受众活动之集客过渡的数据添加到旧数据中。

        警告，如果所更新受众的受众类型或定向维度与工作流的当前配置不兼容，则此选项会导致出错。例如，您无法使用来自查询的用户档案填充文件类型受众。

   * **[!UICONTROL Create a new audience]**：输入所创建受众的名称。创建受众的时间和日期将自动添加到受众名称中。这样可让每次执行工作流时，创建的受众具有唯一性。
   * **[!UICONTROL Share in Adobe Experience Cloud]**：如果您已经定向了用户档案，并且要将受众导出到 Adobe Experience Cloud，请选择此选项，然后选择现有共享受众或创建新受众。

     另外，请选择与受众所包含数据资源相对应的 **[!UICONTROL Shared Data source]**，以便在 Adobe Experience Cloud 中正确协调数据。

     使用此选项，不会将共享受众添加到可通过 **[!UICONTROL Audiences]** 菜单访问的 Adobe Campaign 受众列表。

     >[!NOTE]
     >
     >仅当管理员配置了 Adobe Experience Cloud 的共享受众功能时，此选项才可用。有关更多信息，请参阅[使用 Campaign 和 People Core Service](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)。

   在更新期间保存或可用的受众类型，取决于置于工作流上游的活动。

   如果保存时定向维度未知（例如，如果受众来自导入的文件），则创建或更新的受众将采用 **[!UICONTROL File]** 类型。

   如果保存时已经定义了所保存受众的定向维度（例如，如果受众来自定向、查询之后等等），则保存或更新的受众将采用 **[!UICONTROL List]** 类型。

   随后，受众的详细视图中会提供所保存受众的内容，可通过 **[!UICONTROL Audiences]** 菜单访问该视图。该视图中可用的列，对应于工作流中保存受众活动之集客过渡的列。例如：所导入文件的列、从查询添加的其他数据。

1. 确认活动的配置并保存工作流。

## 示例 {#example}

此示例中定义的工作流，展示了来自定向的常规受众更新：

* 使用 **[!UICONTROL Scheduler]**，每月自动执行一次。
* 您可以使用 **[!UICONTROL Query]** 取回订阅了各种可用应用程序服务的所有用户档案。
* **[!UICONTROL Save audience]** 活动可更新受众，其方法为删除自上次工作流执行以来取消订阅服务的用户档案并添加新订阅的用户档案。

![](assets/save_audience_example_1.png)

**[!UICONTROL Save audience]** 活动的配置如下：

![](assets/save_audience_example_2.png)
