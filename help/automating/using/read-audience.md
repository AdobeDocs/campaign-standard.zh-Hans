---
title: 阅读受众
seo-title: 阅读受众
description: 阅读受众
seo-description: 阅读受众活动允许您检索现有受众，并通过应用其他过滤条件来调整受众。
page-status-flag: 从未激活
uuid: 58c54e71-f4 a7-4ae9-80a3-33c379 ab1 db9
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 定位活动
discoiquuid: 674684e5-8830-4d2f-ba97-59ed4 ba7422 f
context-tags: ReadAudience，主要
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Read audience{#read-audience}

## Description {#description}

![](assets/prefill.png)

**[!UICONTROL Read audience]** 活动允许您检索现有受众，并通过应用其他过滤条件来调整现有受众。

## Context of use {#context-of-use}

**[!UICONTROL Read audience]** 活动是为您只需要选择现有受众而设计的 **[!UICONTROL Query]** 活动的一个更简单版本。

## Configuration {#configuration}

1. Drop a **[!UICONTROL Read audience]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Select the audience you want to retrieve from the **[!UICONTROL Properties]** tab.

   You can retrieve audiences of the following types: **[!UICONTROL List]**, **[!UICONTROL Query]**, **[!UICONTROL File]** and **[!UICONTROL Experience Cloud]**. For more information on audience types, refer to the [Audiences](../../audiences/using/about-audiences.md) documentation.

   The **[!UICONTROL Use a dynamic audience]** option lets you define the name of the audience to target based on the workflow's events variables. For more on this, refer to the [Customizing activities with events variables](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) section.

   ![](assets/readaudience_activity1.png)

1. If you want to apply additional filtering to the selected audience, add conditions via the **[!UICONTROL Source filtering]** tab of the activity.

   For more information about creating filtering conditions, refer to the [Creating queries](../../automating/using/editing-queries.md#creating-queries) documentation.

1. 确认活动的配置并保存工作流。

## Example: Reconcile a File audience with the database {#example--reconcile-a-file-audience-with-the-database}

This example shows how to use the **[!UICONTROL Read audience]** activity to reconcile an audience directly created from a file import.

执行文件导入时，您可以直接在受众中保存其内容。此受众是文件受众，其数据没有链接到任何数据库资源。

导入工作流的设计如下：

![](assets/readaudience_activity_example3.png)

* [加载文件](../../automating/using/load-file.md) 活动会上传包含从外部工具提取的配置文件数据的文件。

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

* [节省受众](../../automating/using/save-audience.md) 的活动会将传入的数据另存为受众。由于数据尚未协调，受众是文件受众，而数据也不被视为个人资料数据。

排序工作流的设计如下：

![](assets/readaudience_activity_example2.png)

* **[!UICONTROL Read audience]** 活动上传在导入工作流中创建的文件受众。受众数据尚未与Adobe Campaign数据库协调。
* [“帐帐”](../../automating/using/reconciliation.md) 活动通过 **[!UICONTROL Identification]** 其选项卡将传入的数据标识为配置文件。For example by using the **email** field as reconciliation criteria.
* [更新数据](../../automating/using/update-data.md) 活动使用传入数据插入并更新数据库的配置文件资源。As the data is already identified as profiles, you can select the **[!UICONTROL Directly using the targeting dimension]** option and select **[!UICONTROL Profiles]** in the **[!UICONTROL Identification]** tab of the activity. 然后，您只需添加需要在按选项卡中更新的字段列表。

## Example: Union on two refined audiences {#example--union-on-two-refined-audiences}

The workflow defined in this example shows the union of two **[!UICONTROL Read audience]** activities. 此工作流程的目标是向年龄在18到30岁之间的黄金或银色会员发送电子邮件。

系统中已创建特定受众以跟踪金牌和银牌会员。

工作流的设计如下：

![](assets/readaudience_activity_example1.png)

* A first **[!UICONTROL Read audience]** activity that retrieves the Gold members audience and refines it by selecting only profiles that are between 18 and 30 years old.
* A second **[!UICONTROL Read audience]** activity that retrieves the Silver members audience and refines it by selecting only profiles that are between 18 and 30 years old.
* **[!UICONTROL Union]** 将两个 **[!UICONTROL Read audiences]** 活动中的人员整合到一个最终人口中的活动。
* **[!UICONTROL Email delivery]** 将电子邮件发送给 **[!UICONTROL Union]** 来自活动的人群的活动。

