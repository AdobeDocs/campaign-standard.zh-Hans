---
title: 定义导入模板
description: 利用导入模板，可以减少所需的设置并更快地导入数据。
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '787'
ht-degree: 100%

---


# 定义导入模板{#defining-import-templates}

利用导入模板，管理员可预定义一定数量的技术导入配置。随后，标准用户可以使用这些模板来执行和上传文件。

导入模板由功能管理员定义，并可通过 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Import templates]** 菜单进行管理。

![](assets/import_template_list.png)

提供了三个默认的只读模板：

* **[!UICONTROL Update Direct mail quarantines and delivery logs]**：此模板可用作新导入的基础，用于更新直邮的隔离和投放日志。模板的工作流包含以下活动：
* **[!UICONTROL Import data]**：此模板可用作新导入的基础，用于将来自文件的数据插入数据库。此模板的工作流包含以下活动：

   * **[!UICONTROL Load file]**：此活动用于向 Adobe Campaign 服务器上传文件。
   * **[!UICONTROL Update data]**：此活动用于将来自文件的数据插入数据库。

* **[!UICONTROL Import list]**：此模板可用作新导入的基础，用于根据来自文件的数据创建 **List** 类型受众。此模板的工作流包含以下活动：

   * **[!UICONTROL Load file]**：此活动用于向 Adobe Campaign 服务器上传文件。
   * **[!UICONTROL Reconciliation]**：此活动用于将定向维度链接到导入的数据。然后，您可以创建 **List** 类型受众。如果导入数据的定向维度未知，则受众为 **File** 类型。请参阅[定向维度和资源](../../automating/using/query.md#targeting-dimensions-and-resources)。
   * **[!UICONTROL Save audience]**：此活动允许您以 **List** 类型受众的形式保存导入的数据。所保存受众的名称对应于用户所导入文件的名称，并将添加指明导入日期和时间的后缀。例如：“profiles_20150406_151448”。

这些默认模板属于只读模板，且标准用户不可见。要创建可供用户使用的模板，请执行以下步骤：

1. 复制默认模板。复制的模板包含三个选项卡：

   * **[!UICONTROL Properties]**：导入模板的一般参数。利用此选项卡，可启用模板并上传样例文件。
   * **[!UICONTROL Workflow]**：导入工作流。利用此选项卡，可定义工作流活动。在用户执行的简化导入期间，这些活动不可见。
   * **[!UICONTROL Executed imports]**：使用此模板执行的导入列表。您可以查看使用此模板执行的每次导入的状态、详细信息和结果您可以直接从此列表访问（以透明方式为用户执行的）工作流。

1. 在 **[!UICONTROL Properties]** 选项卡中，重命名模板并添加说明。当模板可用时，用户即可查看说明。

   ![](assets/simplified_import_model1.png)

1. 转到 **[!UICONTROL Workflow]** 选项卡。在此处，您可以根据需要添加新活动，以扩充默认提供的工作流。

   有关如何配置工作流活动的更多信息，请参阅本节中描述的使用案例：[示例：导入工作流模板](../../automating/using/creating-import-workflow-templates.md)。此使用案例可帮助您设置一个可重复使用的工作流，用于导入来自 Adobe Campaign 数据库中 CRM 的用户档案。

1. 保存模板，以便正确考虑工作流的配置。
1. 从 **[!UICONTROL Properties]** 选项卡上传样例文件。上传的文件只能包含将来导入或采样数据所必需的列。利用样例文件中的数据，可在定义工作流后测试简化的导入。

   ![](assets/import_template_sample.png)

   随后，使用模板进行导入的用户便可以使用此样例文件。用户可将其下载到自己的计算机，以执行诸如使用要导入的数据填充模板之类的操作。添加样例文件时，请务必考虑这一点。

1. 保存模板。现在已考虑样例文件。您可以随时将其下载到计算机以检查内容，或通过勾选 **[!UICONTROL Drop a new sample file]** 选项对其进行修改。

   ![](assets/simplified_import_model2.png)

1. 返回 **[!UICONTROL Workflow]** 选项卡并打开 **[!UICONTROL Load file]** 活动，以检查和调整在上一步中上传之样例文件的列配置。
1. 通过启动工作流测试导入。在第 **5** 步上传的样例文件必须包含数据。

   然后，从样例文件中真正导入数据。请确保所使用的数据为较小的虚构数据，以确保您的数据库不会受到破坏。

1. 转到操作栏中可用的工作流执行日志。如果遇到错误，请检查活动是否正确配置。

   ![](assets/simplified_import_model3.png)

1. 在 **[!UICONTROL Properties]** 选项卡中，将 **[!UICONTROL Import template status]** 设置为 **[!UICONTROL Available]**，然后保存模板。要停止使用此模板，可将 **[!UICONTROL Import template status]** 设置为 **[!UICONTROL Archived]**。

可通过重新上传样例文件并检查 **[!UICONTROL Load file]** 配置，修改模板工作流。

现在，导入模板可供用户使用，并可用于上传文件。

**相关主题：**

* [工作流](../../automating/using/get-started-workflows.md)
* [导入和导出数据](../../automating/using/about-data-import-and-export.md)
* [示例：导入工作流模板](../../automating/using/creating-import-workflow-templates.md)

