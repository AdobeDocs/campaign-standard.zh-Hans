---
title: 导入带有导入模板的数据
seo-title: 导入带有导入模板的数据
description: 导入带有导入模板的数据
seo-description: 了解如何收集数据以馈送Campaign数据库。
page-status-flag: 从未激活
uuid: bfc03235-2032-448a-a9 ed-21ff2 a83 fa09
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自动化
content-type: reference
topic-tags: 导入和导出数据
discoiquuid: fb511bb8-6be7-43f6-86ab-94d5cfa3efc9
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Importing data with import templates{#importing-data-with-import-templates}

导入数据允许您收集数据以提供Campaign数据库。

Alternatively to [Workflows](../../automating/using/discovering-workflows.md), Adobe Campaign offers a simplified import function that allows the user to manage certain types of import that were defined by an administrator.

The operating principle is as follows: an **administrator** defines and manages import templates (see [Defining import templates](../../automating/using/defining-import-templates.md)). These import templates are then made available to users with simplified views under the **[!UICONTROL Profiles & audiences]** &gt; **[!UICONTROL Imports]** menu.

因此，这些用户只需选择要执行的导入类型，然后上传文件以导入数据。管理员定义的工作流是透明执行的，用户可以在完成后访问导入结果的详细信息。

>[!NOTE]
>
>Import data function can be managed by users with **[!UICONTROL GENERIC IMPORT (import)]** and **[!UICONTROL WORKFLOW (workflow)]** roles. 有关角色的更多信息，请参考[此部分](../../administration/using/list-of-roles.md)。

可以根据执行它们的模板、执行日期及其执行状态过滤导入。

1. From the imports overview, click the **[!UICONTROL Create]** button. 向导将打开。
1. 选择要执行的导入类型。导入类型对应于可用的导入模板。
1. 如有必要，请将链接到该模板的示例文件下载到您的计算机，以查看要导入的文件中预期的数据类型。
1. 下载包含要在向导中导入的数据的文件。
1. 开始导入。向导将关闭并返回到使用所使用的模板执行的导入列表。
1. 刷新页面并选择刚刚执行的导入以查看执行详细信息。

   ![](assets/simplified_import1.png)

现在提供导入执行的详细信息。导入的文件以及包含被拒绝数据(未导入的数据)的文件可以下载到您的计算机。
