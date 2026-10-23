---
title: 根据自动文件下载更新数据
description: 下方的示例展示了通过依次进行传输文件活动和更新数据活动，自动下载的加载文件活动的结果。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileImport,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 2b21cf45-1c40-4e0e-ae2c-28c9f73e1964
TQID: 'https://experienceleague.adobe.com/q-u5dH48a4wea1yStaF-QekcD9VaS2NjDhWnSQc6QGU'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 79%
---
# 根据自动文件下载更新数据 {#updating-data-automatic-file-download}

加载文件活动主要用于从传输文件活动构造数据，以便将其集成到现有数据中。

下方的示例展示了通过依次进行传输文件活动和更新数据活动，自动下载的加载文件活动的结果。 此工作流旨在使用新轮廓扩充 Adobe Campaign 数据库，或使用从导入文件取回的数据来更新现有轮廓。

![](assets/load_file_workflow_ex1.png)

要构建工作流，请执行以下步骤：

1. 将[传输文件](../../automating/using/transfer-file.md)活动拖放到工作流中。
1. 选择活动，然后使用所显示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按钮将其打开。
1. 以某种方式配置活动，以便它可以取回您想要的文件。 在 **[!UICONTROL Protocol]** 选项卡中，选择 **SFTP**。
1. 选择 **Use connection parameters defined in an external account** 选项。
1. 输入外部帐户的名称。
1. 输入&#x200B;**远程服务器上的文件路径**。

   ![](assets/wkf_file_transfer_07.png)

1. 确认您的活动。
1. 将[加载文件](../../automating/using/load-file.md)活动拖放到您的工作流中，并将其放在&#x200B;**[!UICONTROL Transfer file]**&#x200B;活动之后。
1. 选择活动，然后使用所显示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按钮将其打开。
1. 在 **[!UICONTROL File to load]** 选项卡的 **[!UICONTROL Execution]** 中，勾选 **[!UICONTROL Use the file specified in the inbound transition]** 选项。

   ![](assets/wkf_file_loading8.png)

1. 按照之前指定的方式配置活动。
1. 将[更新数据](../../automating/using/update-data.md)活动拖放到您的工作流中，并将其放在&#x200B;**[!UICONTROL Load file]**&#x200B;活动之后，然后对其进行配置。

启动工作流后，将提取来自上传文件的数据，然后将其用于扩充 Adobe Campaign 数据库。
