---
title: 管理登陆页面表单数据
seo-title: 管理登陆页面表单数据
description: 管理登陆页面表单数据
seo-description: 了解如何管理登录页面表单数据。
page-status-flag: 从未激活
uuid: 5b22ea2-6628-457f-a618-bfc0e5eb93dd
contentOwner: 勒梅特
products: SG_CAMPAIGN/STANDARD
audience: 频道
content-type: 参考
topic-tags: 登陆页面
discoiquuid: 899c7152-f415-4df9-b4b4-5ff3470a4e32
context-tags: landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9cdfafad7a2ac2db59b037962a84aa03568a55e6

---


# 管理登陆页面表单数据{#managing-landing-page-form-data}

## 更改登陆页面表单数据属性{#changing-a-landing-page-form-data-properties}

您可以将数据库字段链接到输入区域、单选按钮或复选框类型块。 为此，请选择该块并在调色板 **[!UICONTROL Form data]** 中输入。

![](assets/delivery_content_9.png)

* 在“ **字段** ”输入区域中，您可以选择要与表单字段链接的数据库字段。
* “必 **选** ”选项仅允许用户在填写了字段后对页面的提交授权。 如果未填写必填字段，则会显示错误消息。

## 映射表单字段 {#mapping-form-fields}

输入字段用于存储或更新Campaign数据库中的数据。 为此，您需要将数据库字段与输入区域、单选按钮或复选框类型块链接起来。 操作步骤：

1. 在登录页面中选择一个块。
1. 完成调 **[!UICONTROL Form data]** 色板中的部分。

   ![](assets/editing_lp_content_4.png)

1. 选择一个数据库字段以与选择区域中的表单字段 **[!UICONTROL Field]** 链接。

   选中该 **[!UICONTROL Mandatory]** 选项后，只有当用户完成了此字段时，才能提交页面。 如果必填字段未完成，则用户验证页面时将显示错误消息。

   >[!NOTE]
   >
   >登陆页面只能映射到配置 **文件**。

1. 通过选择（例如，）或在选择区 **[!UICONTROL Text]**&#x200B;域中 **[!UICONTROL Number]**&#x200B;来定 **[!UICONTROL Date]** 义字段 **[!UICONTROL HTML type of the field]** 类型。

>[!NOTE]
>
>内置登录页面的默认字段已预配置。 您可以根据需要修改它们。

## 将表单链接到服务 {#linking-a-form-to-a-service}

您可以将表单链接到服务，以便配置文件在验证登陆页面时可以订阅特定服务。

通过用于链接登陆页面的参数，您可以指定执行的操作类型以及登陆页面是专门链接到单个服务还是通用。

要选择要链接的服务，您需要：

1. 编辑通过登陆页面功能板中的图 ![](assets/edit_darkgrey-24px.png) 标访问的登陆页面属性，并显示参 **[!UICONTROL Job]** 数。

   ![](assets/lp_edit_properties_button.png)

1. 在下 **[!UICONTROL Subscription]** 拉列 **[!UICONTROL Specific actions]** 表中选择。

   ![](assets/lp_parameters_5.png)

1. 选择 **[!UICONTROL Specific service]** 以将登陆页面链接到单个服务。 如果要对登录页面使用多项服务，请勿选择此选项。

   使用 **[!UICONTROL Specified service in the URL]** 此选项可允许登录页面用于多项服务。 因此，在配置服务时必须引用登陆页面。

## 数据存储与协调{#data-storage-and-reconciliation}

数据协调参数允许您定义在登录页面中输入的数据在用户提交后如何进行管理。

操作步骤：

1. 编辑通过登陆页面功能板中的图 ![](assets/edit_darkgrey-24px.png) 标访问的登陆页面属性，并显示参 **[!UICONTROL Job]** 数。

   ![](assets/lp_parameters_4.png)

1. 选择 **[!UICONTROL Reconciliation key]**:这些数据库字段(例如：电子邮件、名字、姓氏)用于确定访客是否具有Adobe Campaign数据库中已知的配置文件。 这允许您根据定义的更新策略参数更新或创建配置文件。
1. 定义 **[!UICONTROL Form parameter mapping]**:此部分允许您映射登录页面字段参数和对帐密钥中使用的参数。
1. 选择 **[!UICONTROL Update strategy]**:如果对帐密钥恢复了现有的数据库配置文件，您可以选择使用在表单中输入的数据来更新此配置文件，或者改为阻止此更新。
