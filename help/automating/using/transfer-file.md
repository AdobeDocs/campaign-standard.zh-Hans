---
title: 传输文件
seo-title: 传输文件
description: 传输文件
seo-description: 转移文件活动允许您接收或发送文件，测试在Adobe Campaign中存在文件还是列表文件的情况。
page-status-flag: 从未激活
uuid: a2f18118-b681-4310-aee0-9e82179 d2032
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 数据管理活动
discoiquuid: 752f2aed-f897-485e-b329-f3 cc1756 ee8 e
context-tags: FileTransfer，main
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 0fcedd464ae2074e7eda793bbf20cc53ce04f324

---


# Transfer file{#transfer-file}

## Description {#description}

![](assets/file_transfer.png)

**[!UICONTROL Transfer file]** 活动允许您接收或发送文件，测试是否存在文件或在Adobe Campaign中列出文件。

## Context of use {#context-of-use}

将在配置活动时定义数据的提取方式。例如，要加载的文件可能是联系人列表。

You can use this activity to recover data that will then be structured with the **[!UICONTROL Load file]** activity.

## Configuration {#configuration}

1. Drop a **[!UICONTROL Transfer file]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Use the drop-down list in the **[!UICONTROL Action]** field to select one of the following activity actions:

   ![](assets/wkf_file_transfer_01.png)

   * **文件下载**：允许您下载文件。
   * **文件上传**：允许您上传文件。Uploading a file from Adobe Campaign file generates a log entry in the **[!UICONTROL Export audits]** menu. For more information on export audits, refer to the [Auditing exports](../../administration/using/auditing-export-logs.md) section.
   * **测试以查看文件是否存在**：允许您检查是否有文件。
   * **文件列表**：允许您列出Adobe Campaign中的文件。
   根据所选的操作，有一个或多个协议可用：

   * **HTTP**：此协议允许您从外部帐户或URL开始下载文件。

      * Click the **[!UICONTROL Use connection parameters defined in an external account]** option, then select the account you would like and specify the path of the file to download.

         ![](assets/wkf_file_transfer_03.png)

      * Click the **[!UICONTROL Quick configuration]** option, then enter the URL in the field that appears.

         ![](assets/wkf_file_transfer_04.png)
   * **S3**：此协议允许您开始通过Amazon Simple Storage Service(S3)从URL或外部帐户下载文件。

      * 选择外部帐户并指定要下载的文件路径。

         ![](assets/wkf_file_transfer_08.png)
   * **SFTP**：此协议允许您从URL或外部帐户开始下载文件。

      * Click the **[!UICONTROL Use connection parameters defined in an external account]** option, then select the account you would like and specify the path of the file to download.

         ![](assets/wkf_file_transfer_07.png)

         >[!CAUTION]
         >
         >支持通配符。

      * Click the **[!UICONTROL Quick configuration]** option, then enter the URL in the field that appears.
      * If you want to sort the imported files, select the **[!UICONTROL Sort alphanumerically]** option from the **[!UICONTROL Additional options]** section. 随后将按顺序处理文件。

         ![](assets/wkf_file_transfer_sort.png)
   * **Adobe Campaign服务器上存在的文件**：此协议与包含要恢复的文件的存储库相对应。

      元字符或通配符(例如*或？)可用于筛选文件。

      填写此字段并确认您的活动使用此协议。

      >[!NOTE]
      >
      >路径必须相对于Adobe Campaign服务器的存储空间目录。文件位于** sftp&lt; yourbublename&gt;/**目录中。您还无法浏览存储空间上方的目录。For example: **user&lt;yourinstancename&gt;/my_recipients.csv** is correct. **../hello/my_recipients.csv** 不正确。**//myserver/hello/myrecipients.csv** 不正确。
   选择您的协议并填写相关字段。

   The **[!UICONTROL Use a dynamic file path]** option, available for each protocol, lets you use a standard expression and events variables to personalize the name of the file to transfer. For more on this, refer to the [Customizing activities with events variables](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) section.

1. **[!UICONTROL Additional options]** 此部分根据选定的协议提供，允许您向协议中添加参数。您可以：

   * **[!UICONTROL Delete the source files after transfer]**
   * **[!UICONTROL Disable passive mode]**
   * **[!UICONTROL List all files]**：此选项在选择 **[!UICONTROL File listing]** 操作时可用。It allows you to index all the files present on the server in the **vars.filenames** event variable in which the file names are separated by the **'n'** characters.

1. **[!UICONTROL If no files are found]****[!UICONTROL Advanced options]** 如果在启动活动时检测到任何错误或存在的文件，则选项卡的部分允许您配置特定操作。

   您还可以定义重试。工作流执行日志中会显示不同的重试。

   ![](assets/wkf_file_transfer_09.png)

1. 确认活动的配置并保存工作流。

## Historization settings {#historization-settings}

Every time a **[!UICONTROL Transfer file]** activity is executed, it stores the uploaded or downloaded files in a dedicated folder. One folder is created for each **[!UICONTROL Transfer file]** activity of a workflow. 因此，必须能够限制此文件夹的大小，以保留服务器上的物理空间。

To do that, you can define **[!UICONTROL Historization settings]** in the **[!UICONTROL Advanced options]** of the **[!UICONTROL Transfer File]** activity.

**[!UICONTROL Historization settings]** 允许定义活动文件夹的最大文件数或总大小。默认情况下，授权100个文件和50MB。

每次执行活动时，都会按如下方式检查文件夹：

* 只有在执行活动的24小时内创建的文件才会被考虑。
* If the number of files taken into account is greater than the value of the **[!UICONTROL Maximum number of files]** parameter, the oldest files are deleted until the **[!UICONTROL Maximum number of files]** allowed is reached.
* If the total size of files taken into account is greater than the value of the **[!UICONTROL Maximum size (in MB)]** parameter, the oldest files are deleted until the **[!UICONTROL Maximum size (in MB)]** allowed is reached.

>[!NOTE]
如果未再次执行活动，则不会选中或清除其文件夹。记住，传输大型文件时要小心。

## Example {#example}

The following example shows the configuration of a **File transfer** activity which will then be followed by a **Load file** activity then an **Update data** activity. 此工作流程的目标是使用工作流恢复的数据添加或更新Adobe Campaign数据库配置文件。

1. Drag and drop a **Transfer file** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. **[!UICONTROL Protocol]** 在选项卡中，选择 **SFTP**。
1. Select the **Use connection parameters defined in an external account** option.
1. 输入外部帐户的名称。
1. Enter the **File path on the remote server**.

   ![](assets/wkf_file_transfer_07.png)

1. 确认活动并保存工作流程。

