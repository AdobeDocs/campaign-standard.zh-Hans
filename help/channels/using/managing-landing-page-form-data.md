---
solution: Campaign Standard
product: campaign
title: 管理登陆页面表单数据
description: 了解如何管理登陆页面表单数据。
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,main
feature: Landing Pages
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 99%

---


# 管理登陆页面表单数据{#managing-landing-page-form-data}

## 更改登陆页面表单数据属性{#changing-a-landing-page-form-data-properties}

您可以将数据库字段链接到输入区、单选按钮或复选框类型块。要执行此操作，请选择块并在面板中输入 **[!UICONTROL Form data]**。

![](assets/delivery_content_9.png)

* 利用“**字段**”输入区域，您可以选择要与表单字段链接的数据库字段。
* 利用“**必填**”选项，可设置为仅在用户填写字段后才授权页面提交。如果未填写必填字段，则会显示错误消息。

## 映射表单字段{#mapping-form-fields}

可使用输入字段存储或更新 Campaign 数据库中的数据。要执行此操作，您需要将数据库字段链接到输入区、单选按钮或复选框类型块。操作步骤：

1. 在登陆页面中选择块。
1. 填写面板中的 **[!UICONTROL Form data]** 部分。

   ![](assets/editing_lp_content_4.png)

1. 选择要与 **[!UICONTROL Field]** 选区中的表单字段链接的数据库字段。登陆页面只能映射&#x200B;**用户档案**。

1. 需要时，可勾选 **[!UICONTROL Mandatory]** 选项。只有用户填写了此字段后，才可提交页面。如果未填写必填字段，则用户验证页面时会显示错误消息。

1. 通过 **[!UICONTROL HTML type of the field]** 选区定义字段类型，例如可选择 **[!UICONTROL Text]**、**[!UICONTROL Number]** 或 **[!UICONTROL Date]**。
如果选择“必填”**[!UICONTROL Checkbox]**，请确保其类型为 **[!UICONTROL Field]**。

>[!NOTE]
>
>内置登陆页面的默认字段已进行了预配置。您可以根据需要对其进行修改。

## 数据存储与协调{#data-storage-and-reconciliation}

利用数据协调参数，可定义在用户提交数据后如何管理在登陆页面中输入的数据。

操作步骤：

1. 编辑通过登陆页面仪表板中的 ![](assets/edit_darkgrey-24px.png) 图标访问的登陆页面属性，并显示 **[!UICONTROL Job]** 参数。

   ![](assets/lp_parameters_4.png)

1. 选择 **[!UICONTROL Reconciliation key]**：这些数据库字段（例如：电子邮件、名字、姓氏）用于确定访客的用户档案是否已存在于 Adobe Campaign 数据库中。这样可让您根据定义的更新策略参数，更新或创建用户档案。
1. 定义 **[!UICONTROL Form parameter mapping]**：利用此部分可映射登陆页面字段参数和协调键值中使用的参数。
1. 选择 **[!UICONTROL Update strategy]**：如果协调键值取回了现有的数据库用户档案，您可以选择使用在表单中输入的数据来更新此用户档案，或者改为阻止此更新。
