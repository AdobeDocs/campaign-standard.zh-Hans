---
title: 更新数据
description: “更新”数据活动允许您对数据库中的字段执行成批更新。
page-status-flag: 从未激活
uuid: 1dc55db5-affd-4688-b673-adfb8c1338b5
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 自动化
content-type: 参考
topic-tags: 数据管理活动
discoiquuid: 4db83c95-4b75-4a16-8dbf-bd8940431fa9
context-tags: 作者，主
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 更新数据{#update-data}

## 说明 {#description}

![](assets/data_update.png)

活动 **[!UICONTROL Update data]** 允许您对数据库中的字段执行成批更新。

## 使用环境 {#context-of-use}

在导 **入文件后** ，可以使用“更新数据”活动，以将恢复的数据插入Adobe Campaign数据库。 通过几个选项，您可以个性化更新数据。

## 配置 {#configuration}

1. 将活动拖放 **[!UICONTROL Update data]** 到工作流中。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮将其打开。
1. 指定 **[!UICONTROL Operation type]** 要执行的操作：

   * **[!UICONTROL Insert or update]**:插入数据或更新数据（如果数据库中已存在记录）。
   * **[!UICONTROL Insert only]**:仅插入数据。 不更新已存在的记录。 如果定义了调节标准，则只会添加未调节的记录。

      如果导 **[!UICONTROL Generate an outbound transition for rejects]** 入的数据包含数据库中已存在的某些记录，请选中此框以避免出现任何可能的错误。

   * **[!UICONTROL Update]**:更新仅存在于数据库中的记录的数据。
   * **[!UICONTROL Delete]**:删除数据。
   >[!NOTE]
   >
   >该字 **[!UICONTROL Batch size]** 段允许您为要上传的数据定义最大批量大小。

1. 在选项卡 **[!UICONTROL Identification]** 中，指定如何标识数据库中的记录：

   * **[!UICONTROL Using the targeting dimension]**:选择 **[!UICONTROL Dimension to update]** ，然后指定 **[!UICONTROL Keys for finding records]**。 有关详细信息，请参阅定 [位维和资源](../../automating/using/query.md#targeting-dimensions-and-resources)。
   * 如果输入的数据与现有定位维匹配，请选择该 **[!UICONTROL Using one or more links]** 选项。 然后选择 **[!UICONTROL Dimension to update]**。
   如果所选操作类型需要更新，则必须使用对帐密钥。

1. 在选 **[!UICONTROL Fields to update]** 项卡中，指定将应用更新的字段，并根据需要添加条件以执行此更新。 为此，请使用 **[!UICONTROL Taken into account if]** 列。 这些条件按列表顺序依次应用。 使用右侧的箭头更改更新的顺序。 您可以多次使用同一目标字段。

   您可以使用按钮自动链接字 ![](assets/wkf_magic_wand-24px.png) 段。 自动链接会检测名称相同的字段。

   在类型操 **[!UICONTROL Insert or update]** 作期间，您可以单独选择要应用于每个字段的操作。 为此，请在列中选择所需的 **[!UICONTROL Operation]** 值。

   >[!NOTE]
   >
   >**管理更新** 在运行更新数据活 **[!UICONTROL lastModified]**&#x200B;动时，自动更新、和 **[!UICONTROL modifiedBy]****[!UICONTROL created]****[!UICONTROL createdBy]** 字段，除非在字段更新表中明确执行了这些字段的配置。 只对已检测到至少一个差的记录执行更新。 如果值相同，则不执行更新。

1. 如果需要，可以管理活动的“过 [渡](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) ”以访问出站人群的高级选项。

   如果您已选择并 **[!UICONTROL Insert only]** 且导入的数据可能包含数据库中已存在的记录，请选中该框以避 **[!UICONTROL Generate an outbound transition for the rejects]** 免出现任何可能的错误。

1. 确认活动的配置并保存工作流。

## Example {#example}

以下活动显示了活动后 **[!UICONTROL Update data]** 的活动的配 **[!UICONTROL Load file]** 置。 此工作流程的目的是使用从文件恢复的数据向Adobe Campaign数据库添加或更新配置文件。 使用的对帐密钥是电子邮件地址。

加载的文件是包含以 **下示例数据的。txt** 格式文件：

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

活 **[!UICONTROL Update data]** 动配置如下：

![](assets/deduplication_example2_writer1.png)

![](assets/deduplication_example2_writer2.png)

