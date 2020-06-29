---
title: 根据自动文件下载更新数据
description: '以下示例显示通过传输文件活动自动下载的加载文件活动的结果，后跟更新数据活动。 '
page-status-flag: never-activated
uuid: 69af12cc-6f82-4977-9f53-aa7bc26f5d7e
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 584ff893-9b1b-46c9-9628-714ab349ab88
context-tags: fileImport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 0%

---


# 根据自动文件下载更新数据 {#updating-data-automatic-file-download}

负载文件活动主要从传输文件活动构造数据以便将其集成到现有数据中。

以下示例显示通过传输文件活动自动下载的加载文件活动的结果，后跟更新数据活动。 此工作流旨在用新的Adobe Campaign来丰富用户档案库，或使用从导入的文件中恢复的数据来更新现有用户档案库。

![](assets/load_file_workflow_ex1.png)

要构建工作流，请按照以下步骤操作：

1. 将传输文件 [活动拖放](../../automating/using/transfer-file.md) 到您的工作流中。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮打开它。
1. 以某种方式配置活动，以恢复您想要的文件。 在选项 **[!UICONTROL Protocol]** 卡中，选 **择SFTP**。
1. 选择“ **使用在外部帐户中定义的连接参数** ”选项。
1. 输入外部帐户的名称。
1. 输入远 **程服务器上的文件路径**。

   ![](assets/wkf_file_transfer_07.png)

1. 确认您的活动。
1. 将加载文件 [活动拖放](../../automating/using/load-file.md) 到您的工作流中，并将其放在 **[!UICONTROL Transfer file]** 活动之后。
1. 选择活动，然后使用显示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按钮打开它。
1. 在选 **[!UICONTROL File to load]** 项卡的部 **[!UICONTROL Execution]** 分中，选中 **[!UICONTROL Use the file specified in the inbound transition]** 选项。

   ![](assets/wkf_file_loading8.png)

1. 按照之前指定的方式配置活动。
1. 将更新活动拖 [放到您的工作](../../automating/using/update-data.md) 流中，并将其放在该活动之 **[!UICONTROL Load file]** 后，再进行配置。

启动工作流后，将提取来自已上载文件的数据，然后用于丰富Adobe Campaign数据库。
