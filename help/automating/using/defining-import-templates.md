---
title: 定义导入模板
description: 导入模板可以减少所需的设置并更快地导入数据。
page-status-flag: never-activated
uuid: 651eb57c-adac-4e3e-b454-b39aea1f0484
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: 85d13147-fb31-446a-8476-f112c841fb82
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# 定义导入模板{#defining-import-templates}

导入模板允许管理员预定义一定数量的技术导入配置。 标准用户随后可以使用这些模板来执行和上传文件。

导入模板由职能管理员定义，并可在> >菜单 **[!UICONTROL Resources]** 下 **[!UICONTROL Templates]** 进行 **[!UICONTROL Import templates]** 管理。

![](assets/import_template_list.png)

有三个默认的只读模板可用：

* **[!UICONTROL Update Direct mail quarantines and delivery logs]**: 此模板可用作新导入的基础，用于更新直邮隔离和投放日志。 模板的工作流包含以下活动:
* **[!UICONTROL Import data]**: 此模板可用作新导入的基础，用于将文件中的数据插入数据库。 此模板的工作流包含以下活动:

   * **[!UICONTROL Load file]**: 此活动允许您在Adobe Campaign服务器上上传文件。
   * **[!UICONTROL Update data]**: 此活动允许您在数据库中插入来自文件的数据。

* **[!UICONTROL Import list]**: 此模板可用作新导入的基础，以从文件中的 **列表** 创建类型受众。 此模板的工作流包含以下活动:

   * **[!UICONTROL Load file]**: 此活动允许您在Adobe Campaign服务器上上传文件。
   * **[!UICONTROL Reconciliation]**: 此活动允许您将定位维度链接到导入的数据。 然后，您可以创建 **列表** 类型受众。 如果导入数据的定位维度未知，则受众为“文件 **类型** ”。 请参 [阅定位维度和资源](../../automating/using/query.md#targeting-dimensions-and-resources)。
   * **[!UICONTROL Save audience]**: 此活动允许您以列表类型受众的形式保 **存** 导入的数据。 保存的受众的名称与用户导入的文件的名称相对应，并将添加一个后缀，指定导入的日期和时间。 例如： &#39;用户档案_20150406_151448&#39;。

这些默认模板为只读模板，标准用户不可见。 要创建可供用户使用的模板，请执行以下步骤：

1. 重复默认模板。 复制的模板包含三个选项卡：

   * **[!UICONTROL Properties]**: 导入模板的一般参数。 此选项卡允许您启用模板并上传示例文件。
   * **[!UICONTROL Workflow]**: 导入工作流。 此选项卡允许您定义工作流活动。 这些活动在用户进行的简化导入过程中不可见。
   * **[!UICONTROL Executed imports]**: 使用此模板执行的导入列表。 您可以视图使用此模板执行的每个导入的状态、详细信息和结果。 您可以直接从此列表访问工作流（以透明方式为用户执行）。

1. 在选项卡 **[!UICONTROL Properties]** 中，重命名模板并添加说明。 当模板可用时，用户将能够视图描述。

   ![](assets/simplified_import_model1.png)

1. 转到选 **[!UICONTROL Workflow]** 项卡。 在此处，您可以根据需要添加新活动，以丰富默认提供的工作流。

   有关如何配置工作流活动的详细信息，请参阅本节中描述的用例： [示例： 导入工作流模板](../../automating/using/importing-data.md#example--import-workflow-template)。 此用例将帮助您设置一个工作流，它可重用于导入来自用户档案库中CRM的Adobe Campaign。

1. 保存模板，以便正确考虑工作流的配置。
1. 从选项卡上传示例 **[!UICONTROL Properties]** 文件。 上传的文件只能包含将来导入或示例数据所必需的列。 示例文件中的数据允许您在定义工作流后测试简化的导入。

   ![](assets/import_template_sample.png)

   随后，使用模板进行导入的用户便可以使用此示例文件。 他们将能够将其下载到自己的计算机，例如用要导入的数据填充它。 添加示例文件时，请务必考虑这一点。

1. 保存模板。 现在已考虑示例文件。 您可以随时将其下载到计算机以检查内容，或通过选中选项对其进行 **[!UICONTROL Drop a new sample file]** 修改。

   ![](assets/simplified_import_model2.png)

1. 返回选项卡 **[!UICONTROL Workflow]** 并打开活动 **[!UICONTROL Load file]** ，以检查和调整在上一步上传的示例文件的列配置。
1. 通过启动工作流测试导入。 在步骤5上传的示例 **文件** 必须包含数据。

   然后，从示例文件中真正导入数据。 请确保所使用的数据是小的和虚构的，以确保您的数据库不会受到破坏。

1. 转到操作栏中可用的工作流执行日志。 如果遇到错误，请检查活动配置是否正确。

   ![](assets/simplified_import_model3.png)

1. 在选 **[!UICONTROL Properties]** 项卡中，将 **[!UICONTROL Import template status]** 设置 **[!UICONTROL Available]**&#x200B;为，然后保存模板。 要停止使用此模板，可将 **[!UICONTROL Import template status]** 设置 **[!UICONTROL Archived]**&#x200B;为。

可通过重新上传示例文件并检查配置来修改模板工 **[!UICONTROL Load file]** 作流。

该导入模板现在可供用户使用，并可用于上传文件。

**相关主题：**

* [工作流](../../automating/using/get-started-workflows.md)
* [导入数据](../../automating/using/importing-data.md)
* [示例： 导入工作流模板](../../automating/using/importing-data.md#example--import-workflow-template)

