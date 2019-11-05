---
title: 使用导入模板导入数据
description: 了解如何收集数据以提供Campaign数据库。
page-status-flag: 从未激活
uuid: bfc03235-2032-448a-a9ed-21ff2a83fa09
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 自动化
content-type: 参考
topic-tags: 导入和导出数据
discoiquuid: fb511bb8-6be7-43f6-86ab-94d5cfa3efc9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 使用导入模板导入数据{#importing-data-with-import-templates}

导入数据允许您收集数据以提供Campaign数据库。

或者， [Adobe Campaign](../../automating/using/discovering-workflows.md)还提供了简化的导入功能，允许用户管理管理员定义的某些类型的导入。

其工作原理如下：管理 **员定义** ，并管理导入模板(请参阅 [定义导入模板](../../automating/using/defining-import-templates.md))。 然后，这些导入模板会提供给在“ **[!UICONTROL Profiles & audiences]** &gt;”菜单下具有简化视图的用 **[!UICONTROL Imports]** 户使用。

因此，这些用户只需选择要执行的导入类型，并上传包含要导入的数据的文件。 管理员定义的工作流对用户透明地执行，用户在完成导入后可以访问导入结果的详细信息。

>[!NOTE]
>
>导入数据功能可以由具有和角色的用户 **[!UICONTROL GENERIC IMPORT (import)]** 进行 **[!UICONTROL WORKFLOW (workflow)]** 管理。 有关角色的更多信息，请参考[此部分](../../administration/using/list-of-roles.md)。

可以根据执行导入的模板、导入的执行日期和导入的执行状态来筛选导入。

1. 在导入概述中，单击按 **[!UICONTROL Create]** 钮。 此时将打开向导。
1. 选择要执行的导入类型。 导入类型与可用的导入模板相对应。
1. 如有必要，请将链接到模板的示例文件下载到您的计算机，以查看要导入的文件中所需的数据类型。
1. 下载包含要在向导中导入的数据的文件。
1. 开始导入。 向导将关闭并带您返回使用所用模板执行的导入列表。
1. 刷新页面并选择您刚刚执行的导入，以查看执行详细信息。

   ![](assets/simplified_import1.png)

导入执行的详细信息现在可用。 导入的文件以及包含拒绝的数据（未导入的数据）的文件均可下载到您的计算机。
