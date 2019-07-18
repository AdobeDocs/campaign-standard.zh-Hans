---
title: 定义导入模板
seo-title: 定义导入模板
description: 定义导入模板
seo-description: 导入模板可减少所需的设置并更快地导入数据。
page-status-flag: 从未激活
uuid: 651eb57c-adac-4e3 e-b454-b39 aea1 f0484
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 导入和导出数据
discoiquuid: 85d13147-fb31-446a-8476-f112 c841 fb82
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# Defining import templates{#defining-import-templates}

导入模板允许管理员预定义一定数量的技术导入配置。这些模板随后可供标准用户执行并上传文件。

An import template is defined by the functional administrator and can be managed under the **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Import templates]** menu.

![](assets/import_template_list.png)

提供了三个默认的只读模板：

* **[!UICONTROL Update Direct mail quarantines and delivery logs]**：此模板可用作新导入的基础，用于更新Quarants和提交日志以供直接邮寄。模板的工作流包含以下活动：
* **[!UICONTROL Import data]**：此模板可用作新导入将数据从文件插入数据库的基础。此模板的工作流程包含以下活动：

   * **[!UICONTROL Load file]**：此活动允许您在Adobe Campaign服务器上上传文件。
   * **[!UICONTROL Update data]**：此活动允许您从数据库中的文件插入数据。

* **[!UICONTROL Import list]**：此模板可用作新导入的基础，以便从文件中的数据创建 **列表** 类型受众。此模板的工作流程包含以下活动：

   * **[!UICONTROL Load file]**：此活动允许您在Adobe Campaign服务器上上传文件。
   * **[!UICONTROL Reconciliation]**：此活动允许您将定位维度关联到导入的数据。This then allows you to create a **List** type audience. If the targeting dimension of the imported data is not known, the audience is **File** type. See [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources).
   * **[!UICONTROL Save audience]**：此活动允许您保存以 **列表** 类型受众形式导入的数据。保存的受众的名称与用户导入的文件名称对应，并将增加指定导入日期和时间的后缀。例如：“profiles_20150406_151448”。

这些默认模板为只读模板，对于标准用户不可见。要创建可供用户使用的模板，请按照以下步骤操作：

1. 复制默认模板。复制的模板包含三个选项卡：

   * **[!UICONTROL Properties]**：导入模板的常规参数。此选项卡允许您启用模板并上传示例文件。
   * **[!UICONTROL Workflow]**：导入工作流。此选项卡允许您定义工作流活动。这些活动在用户执行的简化导入过程中不可见。
   * **[!UICONTROL Executed imports]**：使用此模板执行的导入列表。您可以查看使用此模板执行的每个导入的状态、详细信息和结果。您可以从此列表中直接访问工作流(以透明方式进行)。

1. From the **[!UICONTROL Properties]** tab, rename the template and add a description. 当模板可用时，用户将能够查看说明。

   ![](assets/simplified_import_model1.png)

1. Go to the **[!UICONTROL Workflow]** tab. 在此，您可以根据需要添加新活动，从而丰富默认提供的工作流。

   For more on how to configure the workflow activities, refer to the use case describe in this section: [Example: Import workflow template](../../automating/using/importing-data.md#example--import-workflow-template). 此用例将帮助您设置一个工作流，该工作流可重用于从Adobe Campaign数据库中的CRM导入配置文件。

1. 保存模板，以便正确考虑工作流的配置。
1. Upload a sample file from the **[!UICONTROL Properties]** tab. 上传的文件只能具有将来导入或示例数据所需的列。示例文件中的数据允许您在定义工作流后测试简化的导入。

   ![](assets/import_template_sample.png)

   随后，此示例文件将可供使用模板进行导入的用户使用。他们将能够将其下载到自己的计算机上，例如用数据填充它。请确保在添加示例文件时考虑这一点。

1. 保存模板。现在会考虑示例文件。At any moment you can download it to your computer to check the content, or modify it by checking the **[!UICONTROL Drop a new sample file]** option.

   ![](assets/simplified_import_model2.png)

1. Go back to the **[!UICONTROL Workflow]** tab and open the **[!UICONTROL Load file]** activity to check and adjust the column configuration of the sample file that was uploaded at the previous step.
1. 通过启动工作流测试导入。The sample file uploaded at step **5** has to contain data.

   随后实际上会导入示例文件中的数据。请确保使用的数据小且虚假，以确保数据库不会受到破坏。

1. 转到操作栏中可用的工作流执行日志。如果遇到错误，请检查是否正确配置了活动。

   ![](assets/simplified_import_model3.png)

1. **[!UICONTROL Properties]** 在选项卡中，将其 **[!UICONTROL Import template status]** 设置 **[!UICONTROL Available]**&#x200B;为，然后保存模板。To stop using this template, you can set the **[!UICONTROL Import template status]** to **[!UICONTROL Archived]**.

The template workflow can be modified by re-uploading the sample file and checking the **[!UICONTROL Load file]** configuration.

导入模板现在可供用户使用，并可用于上传文件。

**相关主题：**

* [工作流](../../automating/using/discovering-workflows.md)
* [导入数据](../../automating/using/importing-data.md)
* [示例：导入工作流模板](../../automating/using/importing-data.md#example--import-workflow-template)

