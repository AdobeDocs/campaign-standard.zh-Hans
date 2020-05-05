---
title: 使用导入模板导入数据
description: 了解如何收集数据以提供活动库。
page-status-flag: never-activated
uuid: bfc03235-2032-448a-a9ed-21ff2a83fa09
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: fb511bb8-6be7-43f6-86ab-94d5cfa3efc9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# 使用导入模板导入数据{#importing-data-with-import-templates}

导入数据允许您收集数据以供应活动的数据库。

或者， [工作流](../../automating/using/get-started-workflows.md),Adobe Campaign优惠一个简化的导入功能，该功能允许用户管理管理员定义的特定类型的导入。

工作原则如下： 管 **理员** 定义和管理导入模板 [(请参阅](../../automating/using/defining-import-templates.md)定义导入模板)。 然后，这些导入模板在>菜单下以简化的视图提供给 **[!UICONTROL Profiles & audiences]** 用户 **[!UICONTROL Imports]** 使用。

因此，这些用户只需选择要执行的导入类型，并上传包含要导入的数据的文件。 管理员定义的工作流是透明地执行给用户的，用户在完成导入后可以访问导入结果的详细信息。

>[!NOTE]
>
>导入数据函数可由具有和角色的用 **[!UICONTROL GENERIC IMPORT (import)]** 户 **[!UICONTROL WORKFLOW (workflow)]** 管理。 有关角色的更多信息，请参考[此部分](../../administration/using/list-of-roles.md)。

可以根据导入的执行模板、执行日期和执行状态过滤导入。

1. 在导入概述中，单击 **[!UICONTROL Create]** 按钮。 此时将打开向导。
1. 选择要执行的导入类型。 导入类型与可用导入模板相对应。
1. 如有必要，请将链接到模板的示例文件下载到您的计算机，以视图要导入的文件中所需的数据类型。
1. 下载包含要在向导中导入的数据的文件。
1. 开始导入。 向导将关闭并带您返回使用所用模板执行的导入列表。
1. 刷新页面并选择刚刚执行的导入以视图执行详细信息。

   ![](assets/simplified_import1.png)

导入执行的详细信息现在可用。 已导入的文件以及包含已拒绝数据（未导入的数据）的文件均可下载到您的计算机。
