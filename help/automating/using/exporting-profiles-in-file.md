---
solution: Campaign Standard
product: campaign
title: 在外部文件中导出用户档案
description: 此用例说明如何以外部文件的形式导出列表用户档案，以便在Adobe Campaign之外使用数据。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileExport,main
feature: 工作流
role: 数据架构师
level: 中间
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 67%

---


# 在外部文件中导出用户档案 {#exporting-profiles-external-file}

下方的示例说明了如何在 **[!UICONTROL Query]** 活动后配置 **[!UICONTROL Extract file]** 活动。

此工作流旨在以外部文件的形式导出用户档案列表，以便在 Adobe Campaign 之外使用该数据。

1. 将[提取文件](../../automating/using/extract-file.md)活动拖放到工作流中，并将其放在[查询](../../automating/using/query.md)活动之后。

   在本例中，就是对 18 至 30 岁的所有用户档案执行查询。

1. 打开&#x200B;**[!UICONTROL Extract file]**&#x200B;活动进行编辑。
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
1. 在&#x200B;**[!UICONTROL Extract file]**&#x200B;活动后拖放[传输文件](../../automating/using/transfer-file.md)活动，以在外部帐户上恢复提取文件。
1. 打开活动并选择 **[!UICONTROL File upload]** 操作。

   ![](assets/wkf_data_export11.png)

1. 选择外部帐户，然后输入服务器上文件夹的路径。

   ![](assets/wkf_data_export12.png)

1. 确认您的活动并保存工作流。
1. 启动工作流。

   正确执行工作流后，即可在外部帐户上使用提取的文件。
