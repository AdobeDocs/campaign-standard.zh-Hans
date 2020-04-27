---
title: 管理登陆页面表单数据
description: 了解如何管理登陆页表单数据。
page-status-flag: never-activated
uuid: 5b222ea2-6628-457f-a618-bfc0e5eb93dd
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: 899c7152-f415-4df9-b4b4-5ff3470a4e32
context-tags: landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8c24e048c698f7ad699e83a753c114fcfd25f6a0

---


# 管理登陆页面表单数据{#managing-landing-page-form-data}

## 更改登陆页表单数据属性{#changing-a-landing-page-form-data-properties}

您可以将数据库字段链接到输入区域、单选按钮或复选框类型块。 为此，请选择该块并在调色板 **[!UICONTROL Form data]** 中输入。

![](assets/delivery_content_9.png)

* 在“ **字段** ”输入区域中，您可以选择要与表单字段链接的数据库字段。
* “必 **选** ”选项仅允许用户在填写了字段后对页面的提交授权。 如果未填写必填字段，则会显示错误消息。

## 映射表单字段 {#mapping-form-fields}

输入字段用于存储或更新活动数据库中的数据。 为此，您需要将数据库字段与输入区域、单选按钮或复选框类型块链接起来。 操作步骤：

1. 在登陆页中选择一个块。
1. 完成调 **[!UICONTROL Form data]** 色板中的部分。

   ![](assets/editing_lp_content_4.png)

1. 选择一个数据库字段以与选择区域中的表单字段 **[!UICONTROL Field]** 链接。 登陆页只能映射为 **用户档案**。

1. 根据需要 **[!UICONTROL Mandatory]** 选中此选项。 仅当用户完成此字段时，才可提交页面。 如果必填字段未完成，则用户验证页面时将显示错误消息。

1. 通过选择（例如，）或在选择区 **[!UICONTROL Text]**&#x200B;域中 **[!UICONTROL Number]**&#x200B;来定 **[!UICONTROL Date]** 义字段 **[!UICONTROL HTML type of the field]** 类型。
如果选择强制 **[!UICONTROL Checkbox]**&#x200B;选项，请确保其类 **[!UICONTROL Field]** 型。

>[!NOTE]
>
>内置登陆页的默认字段已预配置。 您可以根据需要修改它们。

## 数据存储与协调{#data-storage-and-reconciliation}

数据协调参数允许您定义在登陆页中输入的数据在用户提交后如何管理。

操作步骤：

1. 编辑通过登陆页仪表板中的图 ![](assets/edit_darkgrey-24px.png) 标访问的登陆页属性，并显示 **[!UICONTROL Job]** 参数。

   ![](assets/lp_parameters_4.png)

1. 选择 **[!UICONTROL Reconciliation key]**:这些数据库字段(例如：email, first name, last name)用于确定访客是否具有在Adobe Campaign数据库中已知的用户档案。 这允许您根据定义的更新策略参数更新或创建用户档案。
1. 定义 **[!UICONTROL Form parameter mapping]**:此部分允许您映射登陆页字段参数和在合并关键项中使用的参数。
1. 选择 **[!UICONTROL Update strategy]**:如果合并关键项恢复了现有数据库用户档案，您可以选择使用在表单中输入的数据来更新此用户档案，或者改为阻止此更新。
