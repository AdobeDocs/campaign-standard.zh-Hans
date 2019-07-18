---
title: 提取文件
seo-title: 提取文件
description: 提取文件
seo-description: 提取文件活动允许您以外部文件的形式从Adobe Campaign导出数据。
page-status-flag: 从未激活
uuid: 631f0fbd-9e8d-4f77-a338-fcb7 f4 fc1774
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 数据管理活动
discoiquuid: a06509f9-4731-4187-b43 d-3bfa361284 d3
context-tags: FileExport，main
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: e384a0cef325bc01eb5ea050b0f3d926aea9a88f

---


# Extract file{#extract-file}

## Description {#description}

![](assets/export.png)

**[!UICONTROL Extract file]** 活动允许您以外部文件的形式从Adobe Campaign中导出数据。

## Context of use {#context-of-use}

将在配置活动时定义数据的提取方式。

>[!CAUTION]
>
>**[!UICONTROL Extract file]** 活动必须放在 **[!UICONTROL Query]** 活动之后才能使用。

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL Extract file]** activity into your workflow.

   ![](assets/wkf_data_export1.png)

1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Enter the label of the **Output file**. 将自动用创建的日期和时间完成文件的标签，以便它是唯一的。例如：recipients_20150815_081532.txt的生成2015年月15日08：15：32。

   >[!NOTE]
   >
   >It is possible to use the **[!UICONTROL formatDate]** function in this field to specify the file name.

1. If you like, you can zip the output file by selecting **[!UICONTROL Compression]** in the **[!UICONTROL Add a pre-processing step]** field. 输出文件将压缩为GZIP文件(.gz)。
1. Click the ![](assets/add_darkgrey-24px.png) or **[!UICONTROL Add an element]** button to add an output column.

   ![](assets/wkf_data_export2.png)

   此时将打开一个新窗口。

   ![](assets/wkf_data_export3.png)

1. 输入表达式。To do this, you can select an existing expression or create a new one using the **expression editor**.
1. 确认您的表情。

   表达式将添加到输出列。

1. 根据需要创建任意多个列。您可以通过单击其表达式和标签来编辑列。

   如果您正在导出配置文件并希望在外部工具中使用这些配置文件，请确保导出唯一标识符。默认情况下，并非所有配置文件都具有唯一标识符，具体取决于添加到数据库的方式。For more information, refer to the [Generating a unique ID for profiles](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources) section.

1. Click the **[!UICONTROL File structure]** tab to configure the output, date, and number formats for the file that will be exported.

   Check the **[!UICONTROL Export labels instead of internal values of enumerations]** option in case you export enumeration values. 此选项可检索更短的标签，便于理解而不是ID。

1. In the **[!UICONTROL Properties]** tab, select the **[!UICONTROL Do not generate a file if the inbound transition is empty]** option to avoid creating and uploading empty files on SFTP servers if the inbound transition is empty.
1. 确认活动的配置并保存工作流。

## Example {#example}

The following example illustrates how to configure an **[!UICONTROL Extract file]** activity after a **[!UICONTROL Query]** activity.

此工作流程的目的是以外部文件形式导出配置文件列表，以便数据可在Adobe Campaign之外使用。

1. Drag and drop an **[!UICONTROL Extract file]** activity into your workflow and place it after the **[!UICONTROL Query]** activity.

   在此示例中，对18到30的所有配置文件执行查询。

1. 打开提取文件活动以对其进行编辑。
1. 命名输出文件。
1. 添加输出列。

   在此示例中，电子邮件、年龄、出生日期、名字和配置文件的姓氏将添加为输出列。

   ![](assets/wkf_data_export6.png)

1. Click the **[!UICONTROL File structure]** tab to define:

   * CSV输出格式

      ![](assets/wkf_data_export7.png)

   * 日期格式

      ![](assets/wkf_data_export9.png)

1. 确认活动。
1. Drag and drop a **[!UICONTROL Transfer file]** activity after the **[!UICONTROL Extract file]** activity to recover the extract file on an external account.
1. Open the activity and choose the **[!UICONTROL File upload]** action.

   ![](assets/wkf_data_export11.png)

1. 选择外部帐户并在服务器上输入文件夹的路径。

   ![](assets/wkf_data_export12.png)

1. 确认活动并保存工作流程。
1. 启动工作流。

   正确执行工作流后，提取的文件可在外部帐户上使用。

