---
title: 保存受众
description: “保存受众”活动允许您更新现有受众或从工作流中上游计算的人群创建新受众。
page-status-flag: 从未激活
uuid: 8babb173-fa59-44a7-a2a5-49f45ba6bf99
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 自动化
content-type: 参考
topic-tags: 定位活动
discoiquuid: 1f6bb048-7abd-499b-a4b0-187f9492dc47
context-tags: saveAudience，主
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 保存受众{#save-audience}

## 说明 {#description}

![](assets/save_audience.png)

该活 **[!UICONTROL Save audience]** 动允许您更新现有受众或从工作流中上游计算的人群创建新受众。 通过此活动创建或更新的受众是 **List** 或 **File受众** 。 它们会添加到应用程序受众列表中，并通过菜单提供 **[!UICONTROL Audiences]** 它们。

>[!NOTE]
>
>如果通过活动创建的受 **[!UICONTROL Save audience]** 众已经丰富了其他数据，您将无法使用这些数据个性化独立交付。 它们只能从在工作流中执行的分发中使用。

此活动还允许您将配置文件导出为Adobe Experience cloud受众／区段。 这样，您便可以利用其他Adobe Experience cloud解决方案中的这些受众。 有关共享受众的详细信息，请参 [阅使用Campaign和People Core Service](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)。

## 使用环境 {#context-of-use}

该活 **[!UICONTROL Save audience]** 动主要用于通过将人群组转换为可重用的受众来在同一工作流中计算人群组。

## 配置 {#configuration}

1. 将活动 **[!UICONTROL Save audience]** 拖入工作流。
1. 在查询、交叉点、联合或排除等其他定位活动之后连接它。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮将其打开。
1. 选择要执行的操作：

   * **[!UICONTROL Update an existing audience]**:选择现有受众，然后选择更新类型：

      * **[!UICONTROL Replace audience content with new data]**:整个受众内容被替换。 旧数据丢失。 只保留保存的受众活动的入站过渡中的数据。
      * **[!UICONTROL Complete audience with new data]**:保留旧的受众数据，并将保存的受众活动的入站过渡中的数据添加到该数据中。
   * **[!UICONTROL Create then update an audience]**:输入受众的名称，然后选择更新类型。 如果受众尚不存在，则创建该受众。 如果它已存在，则会根据选定的模式更新它：

      * **[!UICONTROL Replace audience content with new data]**:整个受众内容被替换。 旧数据丢失。 只保留保存的受众活动的入站过渡中的数据。

         警告：此选项会清除已更新受众的受众类型和定位维度。

      * **[!UICONTROL Complete audience with new data]**:保留旧的受众数据，并将保存的受众活动的入站过渡中的数据添加到该数据中。

         警告：如果更新的受众类型或定位维度与工作流的当前配置不兼容，则此选项会导致错误。 例如，您无法使用来自查询的配置文件来完成文件类型受众。
   * **[!UICONTROL Create a new audience]**:输入要创建的受众的名称。 创建受众的时间和日期将自动添加到受众名称中。 这使得每次执行工作流时受众都是独一无二的。
   * **[!UICONTROL Share in Adobe Experience Cloud]**:如果您有目标档案，并且要将受众导出到Adobe Experience Cloud，请选择此选项，然后选择现有共享受众或创建新受众。

      另外，选 **[!UICONTROL Shared Data source]** 择与受众中包含的数据资源相对应的资源，以便在Adobe Experience cloud中正确协调数据。

      使用此选项，共享的受众不会添加到通过菜单提供的Adobe Campaign受众列 **[!UICONTROL Audiences]** 表中。

      >[!NOTE]
      >
      >只有在管理员配置了Adobe Experience Cloud的共享受众功能后，此选项才可用。 有关详细信息，请参 [阅使用Campaign和People Core Service](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)。
   在更新过程中保存或可用的受众类型取决于工作流中上游的活动。

   如果保存受众时，其定位维度未知（例如，如果来自导入的文件），则会创建或更新受众作为类型受 **[!UICONTROL File]** 众。

   如果保存时已定义保存的受众的定位维度（例如，如果它来自定位、查询等），则会将受众另存为类型受众或更新为类 **[!UICONTROL List]** 型受众。

   保存的受众的内容随后会显示在受众的详细信息视图中，可以从菜单访问该视 **[!UICONTROL Audiences]** 图。 此视图中可用的列与工作流保存的受众活动的入站过渡的列相对应。 例如：导入文件的列，从查询添加的其他数据。

1. 确认活动的配置并保存工作流。

## Example {#example}

此示例中定义的工作流显示了从定位进行的常规受众更新：

* 它每月使用一个 **[!UICONTROL Scheduler]**
* 您可以使用恢复 **[!UICONTROL Query]** 订阅了不同应用程序服务的所有配置文件。
* 该活 **[!UICONTROL Save audience]** 动通过删除自上次工作流执行以来已从服务中取消订阅的配置文件以及添加新订阅的配置文件来更新受众。

![](assets/save_audience_example_1.png)

活 **[!UICONTROL Save audience]** 动配置如下：

![](assets/save_audience_example_2.png)

