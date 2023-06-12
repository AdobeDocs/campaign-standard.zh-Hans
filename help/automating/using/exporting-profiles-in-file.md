---
title: 在外部文件中导出用户档案
description: 此用例展示了如何以外部文件的形式导出用户档案列表，以便数据可在Adobe Campaign之外使用。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileExport,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 3fc286a9-bba4-4e3d-95cd-600eed4943e7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 68%

---

# 在外部文件中导出用户档案 {#exporting-profiles-external-file}

下方的示例说明了如何在 **[!UICONTROL Query]** 活动后配置 **[!UICONTROL Extract file]** 活动。

此工作流旨在以外部文件的形式导出用户档案列表，以便在 Adobe Campaign 之外使用该数据。

1. 拖放 [提取文件](../../automating/using/extract-file.md) 将活动放入您的工作流中，并将其放在 [查询](../../automating/using/query.md) 活动。

   在本例中，就是对 18 至 30 岁的所有用户档案执行查询。

1. 打开 **[!UICONTROL Extract file]** 活动以编辑它。
1. 为输出文件命名。
1. 添加输出列。

   在本例中，用户档案的电子邮件、年龄、出生日期、名字和姓氏都将添加为输出列。

   ![](assets/wkf_data_export6.png)

1. 单击 **[!UICONTROL File structure]** 选项卡以定义：

   * CSV 输出格式

      ![](assets/wkf_data_export7.png)

   * 日期格式

      ![](assets/wkf_data_export9.png)

1. 确认您的活动。
1. 拖放 [传输文件](../../automating/using/transfer-file.md) 活动之后 **[!UICONTROL Extract file]** 活动，用于在外部帐户上恢复提取文件。
1. 打开活动并选择 **[!UICONTROL File upload]** 操作。

   ![](assets/wkf_data_export11.png)

1. 选择外部帐户，然后输入服务器上文件夹的路径。

   ![](assets/wkf_data_export12.png)

1. 确认您的活动并保存工作流。
1. 启动工作流。

   正确执行工作流后，即可在外部帐户上使用提取的文件。
