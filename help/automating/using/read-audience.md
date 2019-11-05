---
title: 读取受众
description: 阅读受众活动允许您检索现有受众并通过应用其他过滤条件来优化它。
page-status-flag: 从未激活
uuid: 58c54e71-f4a7-4ae9-80a3-33c379ab1db9
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 自动化
content-type: 参考
topic-tags: 定位活动
discoiquuid: 674684e5-8830-4d2f-ba97-59ed4ba7422f
context-tags: readAudience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 读取受众{#read-audience}

## 说明 {#description}

![](assets/prefill.png)

该活 **[!UICONTROL Read audience]** 动允许您检索现有受众并通过应用其他过滤条件来优化它。

## 使用环境 {#context-of-use}

该活 **[!UICONTROL Read audience]** 动是活动的一个更简单的版本， **[!UICONTROL Query]** 专为只需要选择现有受众的情况而设计。

## 配置 {#configuration}

1. 将活动 **[!UICONTROL Read audience]** 拖入工作流。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮将其打开。
1. 从选项卡中选择要检索的受 **[!UICONTROL Properties]** 众。

   您可以检索以下类型的受众： **[!UICONTROL List]**、 **[!UICONTROL Query]****[!UICONTROL File]** 和 **[!UICONTROL Experience Cloud]**。 有关受众类型的更多信息，请参阅“受 [众](../../audiences/using/about-audiences.md) ”文档。

   通过 **[!UICONTROL Use a dynamic audience]** 此选项，您可以根据工作流的事件变量定义要定位的受众名称。 有关此内容的详细信息，请参阅使 [用事件变量自定义活动](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) 。

   ![](assets/readaudience_activity1.png)

1. 如果要对选定受众应用其他筛选，请通过活动的选 **[!UICONTROL Source filtering]** 项卡添加条件。

   有关创建筛选条件的详细信息，请参阅创 [建查询](../../automating/using/editing-queries.md#creating-queries) 文档。

1. 确认活动的配置并保存工作流。

## 示例：协调文件受众与数据库 {#example--reconcile-a-file-audience-with-the-database}

此示例说明如何使用活 **[!UICONTROL Read audience]** 动协调从文件导入直接创建的受众。

执行文件导入时，您可以直接将其内容保存到受众中。 此受众是文件受众，其数据不链接到任何数据库资源。

导入工作流的设计如下：

![](assets/readaudience_activity_example3.png)

* “加 [载文件](../../automating/using/load-file.md) ”活动上传包含从外部工具提取的配置文件数据的文件。

   例如：

   ```
   lastname;firstname;birthdate;email;crmID
   Smith;Hayden;23/05/1989;hayden.smith@example.com;124365
   Mars;Daniel;17/11/1987;dannymars@example.com;123545
   Smith;Clara;08/02/1989;hayden.smith@example.com;124567
   Durance;Allison;15/12/1978;allison.durance@example.com;120987
   Lucassen;Jody;28/03/1988;jody.lucassen@example.com;127634
   Binder;Tom;19/01/1982;tombinder@example.com;128653
   Binder;Tommy;19/01/1915;tombinder@example.com;134576
   Connor;Jade;10/10/1979;connor.jade@example.com;132452
   Mack;Clarke;02/03/1985;clarke.mack@example.com;149876
   Ross;Timothy;04/07/1986;timross@example.com;157643
   ```

* “保 [存受众](../../automating/using/save-audience.md) ”活动会将传入数据保存为受众。 由于尚未协调数据，因此受众是文件受众，其数据尚未被识别为档案数据。

协调工作流的设计如下：

![](assets/readaudience_activity_example2.png)

* 活动 **[!UICONTROL Read audience]** 会上传在导入工作流程中创建的文件受众。 受众数据尚未与Adobe Campaign数据库协调。
* “对 [帐](../../automating/using/reconciliation.md) ”活动通过选项卡将传入数据标识为配置 **[!UICONTROL Identification]** 文件。 例如，使用电子邮件字 **段作为** “对帐标准”。
* “更 [新数据](../../automating/using/update-data.md) ”活动会插入数据库的配置文件资源并更新传入的数据。 由于数据已标识为配置文件，因此您可以选 **[!UICONTROL Directly using the targeting dimension]** 择选项并在活 **[!UICONTROL Profiles]** 动的选 **[!UICONTROL Identification]** 项卡中进行选择。 然后，您只需根据选项卡添加需要更新的字段列表。

## 示例：两个精细受众的联合 {#example--union-on-two-refined-audiences}

此示例中定义的工作流显示了两个活动的联 **[!UICONTROL Read audience]** 合。 此工作流程的目标是向18到30岁的金牌或银牌会员发送电子邮件。

系统中已创建特定受众以跟踪金牌和银牌会员。

工作流设计如下：

![](assets/readaudience_activity_example1.png)

* 第一个活 **[!UICONTROL Read audience]** 动，它检索黄金会员受众并通过仅选择18到30岁之间的档案来优化受众。
* 第二个 **[!UICONTROL Read audience]** 活动可检索银会员受众，并通过仅选择年龄在18到30岁之间的档案来优化受众。
* 一种 **[!UICONTROL Union]** 将两种活动中的人群 **[!UICONTROL Read audiences]** 团结为最终群体的活动。
* 向来 **[!UICONTROL Email delivery]** 自活动的人群发送电子邮件的活动 **[!UICONTROL Union]** 。

