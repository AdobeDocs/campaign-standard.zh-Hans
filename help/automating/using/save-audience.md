---
title: 节省受众
seo-title: 节省受众
description: 节省受众
seo-description: 通过保存受众活动，您可以更新现有受众或从工作流中的上游计算的人群创建新受众。
page-status-flag: 从未激活
uuid: babb173-fa59-44a7-a2 a5-49f45 ba6 bf99
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 定位活动
discoiquuid: 1f6bb048-7abd-499b-a4 b0-187f9492 dc47
context-tags: SaveAudience，主要
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Save audience{#save-audience}

## Description {#description}

![](assets/save_audience.png)

**[!UICONTROL Save audience]** 该活动允许您更新现有受众，或从工作流中上游计算的人群中创建新受众。The audiences created or updated from this activity are **List** or **File** audiences. They are added to the list of application audiences, and are made available via the **[!UICONTROL Audiences]** menu.

>[!NOTE]
>
>If the audience created through the **[!UICONTROL Save audience]** activity has been enriched with additional data, you will not be able to use these data to personalize a standalone delivery. 它们只能用于在工作流中执行的分发。

此活动还允许您将配置文件作为Adobe Experience Cloud受众/区段导出。这样，您就可以在其他Adobe Experience Cloud解决方案中利用这些受众。For more information about shared audiences, refer to [Working with Campaign and People Core Service](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md).

## Context of use {#context-of-use}

**[!UICONTROL Save audience]** 该活动主要用于将在同一工作流程中计算的人口组转换为可重复使用的受众，从而使其在同一工作流程中得以计算。

## Configuration {#configuration}

1. Drop a **[!UICONTROL Save audience]** activity into your workflow.
1. 在其他定位活动(如查询、交叉点、联盟或排除)之后连接它。
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. 选择要执行的操作：

   * **[!UICONTROL Update an existing audience]**：选择现有受众并选择更新类型：

      * **[!UICONTROL Replace audience content with new data]**：将替换整个受众内容。旧数据丢失。只保留保存受众活动的入站过渡中的数据。
      * **[!UICONTROL Complete audience with new data]**：保留旧受众数据，并将保存受众活动的入站过渡中的数据添加到该数据中。
   * **[!UICONTROL Create then update an audience]**：输入受众的名称并选择更新类型。如果受众尚未存在，则会创建该受众。如果它已经存在，则会根据所选的模式更新它：

      * **[!UICONTROL Replace audience content with new data]**：将替换整个受众内容。旧数据丢失。只保留保存受众活动的入站过渡中的数据。

         警告，此选项可删除更新受众的受众类型和定位维度。

      * **[!UICONTROL Complete audience with new data]**：保留旧受众数据，并将保存受众活动的入站过渡中的数据添加到该数据中。

         警告，如果受众类型或受众的定位维度与工作流的当前配置不兼容，此选项会导致错误。例如，您无法使用查询来自的配置文件完成文件类型受众。
   * **[!UICONTROL Create a new audience]**：输入要创建的受众的姓名。创建受众的时间和日期将自动添加到受众姓名。这使得每次执行工作流的受众都很独特。
   * **[!UICONTROL Share in Adobe Experience Cloud]**：如果您有目标档案，并且希望将受众导出到Adobe Experience Cloud，请选择此选项，然后选择现有共享受众或创建新受众。

      Also select a **[!UICONTROL Shared Data source]** that corresponds to the resource of the data contained in the audience so that the data is correctly reconciled in Adobe Experience Cloud.

      Using this option, the shared audience is not added to the list of Adobe Campaign audiences available via the **[!UICONTROL Audiences]** menu.

      >[!NOTE]
      >
      >只有管理员配置了Adobe Experience Cloud的共享受众功能时，此选项才可用。For more information, refer to [Working with Campaign and People Core Service](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md).
   更新过程中保存或可用的受众类型取决于在工作流中放置的活动。

   If the targeting dimension of the audience is unknown when it is saved (for example if it is from an imported file), the audience is created or updated as a **[!UICONTROL File]** type audience.

   If the targeting dimension of the saved audience is already defined when it is saved (for example, if it comes from a targeting, after a query, etc.), then the audience is saved or updated as a **[!UICONTROL List]** type audience.

   The content of the saved audience is then available in the detail view of the audience, which can be accessed from the **[!UICONTROL Audiences]** menu. 此视图中提供的列与工作流的保存受众活动的入站过渡的列相对应。例如：导入的文件的列，以及从查询中添加的其他数据。

1. 确认活动的配置并保存工作流。

## Example {#example}

此示例中定义的工作流显示了从定位到的常规受众更新：

* It is automatically executed once a month using a **[!UICONTROL Scheduler]**.
* You can use a **[!UICONTROL Query]** to recover all the profiles subscribed to the different application services available.
* **[!UICONTROL Save audience]** 活动通过删除自上次工作流执行以来已取消订阅的配置文件和添加新订阅配置文件来更新受众。

![](assets/save_audience_example_1.png)

**[!UICONTROL Save audience]** 活动的配置如下：

![](assets/save_audience_example_2.png)

