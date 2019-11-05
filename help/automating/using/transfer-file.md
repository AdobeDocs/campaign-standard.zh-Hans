---
title: 传输文件
description: “传输文件”活动允许您接收或发送文件，测试是否存在文件，或列出Adobe Campaign中的文件。
page-status-flag: 从未激活
uuid: a2f18118-b681-4310-aee0-9e82179d2032
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 自动化
content-type: 参考
topic-tags: 数据管理活动
discoiquuid: 752f2aed-f897-485e-b329-f3cc1756ee8e
context-tags: fileTransfer,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 传输文件{#transfer-file}

## 说明 {#description}

![](assets/file_transfer.png)

该 **[!UICONTROL Transfer file]** 活动允许您接收或发送文件，测试是否存在文件，或列出Adobe Campaign中的文件。

## 使用环境 {#context-of-use}

在配置活动时，将定义提取数据的方式。 例如，要加载的文件可以是联系人列表。

您可以使用此活动恢复随后将与活动一起构建的数 **[!UICONTROL Load file]** 据。

## 配置 {#configuration}

1. 将活动 **[!UICONTROL Transfer file]** 拖入工作流。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮将其打开。
1. 使用字段中的下拉列 **[!UICONTROL Action]** 表选择以下活动操作之一：

   ![](assets/wkf_file_transfer_01.png)

   * **文件下载**:允许您下载文件。
   * **文件上传**:允许您上传文件。 从Adobe Campaign文件上传文件将在菜单中生成日志 **[!UICONTROL Export audits]** 条目。 有关导出审核的详细信息，请参阅“审核 [导出](../../administration/using/auditing-export-logs.md) ”一节。
   * **测试以查看文件是否存在**:允许您检查是否有文件。
   * **文件列表**:允许您列出Adobe Campaign中存在的文件。
   根据所选操作，可以使用一个或多个协议：

   * **HTTP**:此协议允许您从外部帐户或URL开始下载文件。

      * 单击 **[!UICONTROL Use connection parameters defined in an external account]** 选项，然后选择所需的帐户并指定要下载的文件的路径。

         ![](assets/wkf_file_transfer_03.png)

      * 单击选 **[!UICONTROL Quick configuration]** 项，然后在显示的字段中输入URL。

         ![](assets/wkf_file_transfer_04.png)
   * **S3**:此协议允许您通过Amazon Simple Storage Service(S3)从URL或外部帐户开始下载文件。

      * 选择外部帐户并指定要下载的文件的路径。

         ![](assets/wkf_file_transfer_08.png)
   * **SFTP**:此协议允许您从URL或外部帐户开始下载文件。

      * 单击 **[!UICONTROL Use connection parameters defined in an external account]** 选项，然后选择所需的帐户并指定要下载的文件的路径。

         ![](assets/wkf_file_transfer_07.png)

         >[!CAUTION]
         >
         >支持通配符。

      * 单击选 **[!UICONTROL Quick configuration]** 项，然后在显示的字段中输入URL。
      * 如果要对导入的文件进行排序，请从部 **[!UICONTROL Sort alphanumerically]** 分中选择选 **[!UICONTROL Additional options]** 项。 然后将按顺序处理文件。

         ![](assets/wkf_file_transfer_sort.png)
   * **Adobe Campaign服务器上存在的文件**:此协议对应于包含要恢复的文件的存储库。

      元字符或通配符（例如*或？）可用于筛选文件。

      填写此字段并确认您使用本协议的活动。

      >[!NOTE]
      >
      >路径必须相对于Adobe Campaign服务器的存储空间目录。 文件位于 **sftp&lt;yourinstancename&gt;/目录** 。 您也无法浏览存储空间上方的目录。 例如： **user&lt;yourinstancename&gt;/my_recipients.csv** is correct. **../hello/my_recipients.csv** is incorrect. **//myserver/hello/myrecipients.csv** is incorrect.
   选择协议并填写相关字段。

   该选 **[!UICONTROL Use a dynamic file path]** 项适用于每个协议，允许您使用标准表达式和事件变量来个性化要传输的文件的名称。 有关此内容的详细信息，请参阅使 [用事件变量自定义活动](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) 。

1. 根据 **[!UICONTROL Additional options]** 所选的协议，此部分可用，允许您向协议添加参数。 您可以：

   * **[!UICONTROL Delete the source files after transfer]**
   * **[!UICONTROL Disable passive mode]**
   * **[!UICONTROL List all files]**:选择操作时，此选项可 **[!UICONTROL File listing]** 用。 它允许您在 **vars.filenames事件变量中索引服务器上存在的所有文件，在该事件变量中，文件名以“n** ”字符分隔 **** 。

1. 在启 **[!UICONTROL If no files are found]** 动活动时， **[!UICONTROL Advanced options]** 选项卡的部分允许您配置特定操作（如果检测到任何错误或不存在的文件）。

   您还可以定义重试次数。 不同的重试次数显示在工作流执行日志中。

   ![](assets/wkf_file_transfer_09.png)

1. 确认活动的配置并保存工作流。

## 历史记录设置 {#historization-settings}

每次执行 **[!UICONTROL Transfer file]** 活动时，都会将上传或下载的文件存储在专用文件夹中。 将为工作流的每个活动 **[!UICONTROL Transfer file]** 创建一个文件夹。 因此，必须能够限制此文件夹的大小以保留服务器上的物理空间。

为此，您可以在活 **[!UICONTROL Historization settings]** 动中 **[!UICONTROL Advanced options]** 定义 **[!UICONTROL Transfer File]** 。

**[!UICONTROL Historization settings]** 允许为活动的文件夹定义最大文件数或总大小。 默认情况下，授权100个文件和50 MB。

每次执行活动时，都会按如下方式检查文件夹：

* 只有在执行活动之前24小时以上创建的文件才会被考虑在内。
* 如果考虑的文件数大于参数的值，则删除最旧的文 **[!UICONTROL Maximum number of files]** 件，直到达到允许的 **[!UICONTROL Maximum number of files]** 值为止。
* 如果考虑的文件的总大小大于参数的值，则删除最旧的文件，直到达到允许的 **[!UICONTROL Maximum size (in MB)]****[!UICONTROL Maximum size (in MB)]** 值为止。

>[!NOTE]
如果不再执行活动，则不会检查或清除其文件夹。 考虑到这一点，在传输大文件时要小心。

## Example {#example}

以下示例显示了文件传输活 **动的配置** ，该活动后跟 **Load file** activity（加载文件活动） **和Update data** activity（更新数据活动）。 此工作流的目标是使用工作流恢复的数据添加或更新Adobe Campaign数据库配置文件。

1. 将“传输文件” **活动拖放到您的工作** 流中。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮将其打开。
1. 在选项卡 **[!UICONTROL Protocol]** 中，选择 **SFTP**。
1. 选择使用 **在外部帐户中定义的连接参数** 。
1. 输入外部帐户的名称。
1. 输入远程 **服务器上的文件路径**。

   ![](assets/wkf_file_transfer_07.png)

1. 确认活动并保存工作流。

