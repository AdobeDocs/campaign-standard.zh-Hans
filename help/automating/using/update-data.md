---
title: 更新数据
seo-title: 更新数据
description: 更新数据
seo-description: 更新数据活动允许您对数据库中的字段执行大规模更新。
page-status-flag: 从未激活
uuid: 1dc55db5-afd-4688-b673-adfb8 c1338 b5
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 数据管理活动
discoiquuid: 4db83c95-4b75-4dbf-bd8940431 fa9
context-tags: 作者，主要
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Update data{#update-data}

## Description {#description}

![](assets/data_update.png)

**[!UICONTROL Update data]** 活动允许您对数据库中的字段执行大规模更新。

## Context of use {#context-of-use}

The **Update data** activity can be used after importing a file in order to insert the data recovered into the Adobe Campaign database. 有几个选项允许您个性化数据。

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL Update data]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Specify the **[!UICONTROL Operation type]** to be carried out:

   * **[!UICONTROL Insert or update]**：插入数据或更新数据，如果数据库中已存在记录。
   * **[!UICONTROL Insert only]**：插入数据。已存在的记录不会更新。如果定义了调解条件，则只会添加未协调的记录。

      Check the **[!UICONTROL Generate an outbound transition for rejects]** box if the data imported contains certain records that already exist in the database to avoid any possible errors.

   * **[!UICONTROL Update]**：更新数据库中已存在记录的数据。
   * **[!UICONTROL Delete]**：删除数据。
   >[!NOTE]
   >
   >**[!UICONTROL Batch size]** 字段允许您定义要上传的数据的最大批次大小。

1. In the **[!UICONTROL Identification]** tab, specify how to identify the records in the database:

   * **[!UICONTROL Using the targeting dimension]**：选择 **[!UICONTROL Dimension to update]** 然后指定 **[!UICONTROL Keys for finding records]**。For more this, refer to [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources).
   * If the data entered matches an existing targeting dimension, select the **[!UICONTROL Using one or more links]** option. Then select the **[!UICONTROL Dimension to update]**.
   如果所选操作类型需要更新，则必须使用对帐密钥。

1. **[!UICONTROL Fields to update]** 在选项卡中，指定将应用更新的字段，并在必要时添加条件以执行此更新。To do this, use the **[!UICONTROL Taken into account if]** column. 条件按列表顺序逐个应用。使用右侧箭头更改更新的顺序。您可以多次使用同一目标字段。

   You can automatically link fields using the ![](assets/wkf_magic_wand-24px.png) button. 自动链接会检测具有相同名称的字段。

   **[!UICONTROL Insert or update]** 在类型操作期间，您可以单独选择要为每个字段应用的操作。To do this, select the value you would like in the **[!UICONTROL Operation]** column.

   >[!NOTE]
   >
   >**管理更新，** 运行更新数据活动时，系统会自动更新 **[!UICONTROL lastModified]**、 **[!UICONTROL modifiedBy]****[!UICONTROL created]****[!UICONTROL createdBy]** 和字段，除非其配置在字段更新表中显式执行。仅在检测到至少一个差异的记录上执行更新。如果这些值相同，则不执行更新。

1. If needed, manage the activity's [Transitions](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) to access the advanced options for the outbound population.

   If you have selected **[!UICONTROL Insert only]** and the data imported may contain records that are already present in the database, check the **[!UICONTROL Generate an outbound transition for the rejects]** box to avoid any possible errors.

1. 确认活动的配置并保存工作流。

## Example {#example}

The following activity shows the configuration of an **[!UICONTROL Update data]** activity following a **[!UICONTROL Load file]** activity. 此工作流程的目的是使用从文件中检索的数据向Adobe Campaign数据库添加或更新配置文件。使用的帐单键是电子邮件地址。

The file loaded is a **.txt** format file containing the following example data:

```
lastname;firstname;email;birthdate
jackman;megan;megan.jackman@testmail.com;07/08/1975
phillips;edward;phillips@testmail.com;09/03/1986
weaver;justin;justin_w@testmail.com;11/15/1990
martin;babeth;babeth_martin@testmail.net;11/25/1964
reese;richard;rreese@testmail.com;02/08/1987
cage;nathalie;cage.nathalie227@testmail.com;07/03/1989
xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992
grimes;daryl;daryl_890@testmail.com;12/06/1979
tycoon;tyreese;tyreese_t@testmail.net;10/08/1971
```

**[!UICONTROL Update data]** 活动的配置如下：

![](assets/deduplication_example2_writer1.png)

![](assets/deduplication_example2_writer2.png)

