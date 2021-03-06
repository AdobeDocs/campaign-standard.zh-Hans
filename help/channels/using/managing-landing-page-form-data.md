---
title: 管理登陆页面表单数据
description: 了解如何管理登陆页面表单数据。
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,main
feature: Landing Pages
role: User
level: Intermediate
exl-id: 7083447c-4cac-41cb-8453-369819e0c7c1
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '835'
ht-degree: 15%

---

# 管理登陆页面表单数据{#managing-landing-page-form-data}

在登陆页内容中，使用输入字段存储或更新Campaign数据库中的数据。

要实现此目的，必须将这些字段映射到数据库字段。

您可以通过 **[!UICONTROL Form data]** 中找到的问题。

![](assets/lp_form-data.png)

## 映射表单字段 {#mapping-form-fields}

要根据您的需求更新Campaign数据库，请将相关数据库字段链接到登陆页面的输入区、单选按钮或复选框类型块。

为此请执行以下操作步骤：

1. 在登陆页面内容中选择块。

   >[!NOTE]
   >
   >内置登陆页面的默认字段已进行了预配置。您可以根据需要对其进行修改。

1. 访问 **[!UICONTROL Form data]** 中找到的问题。

1. 要更改字段类型，请从 **[!UICONTROL HTML type of the field]** 下拉列表。

   ![](assets/lp_html-field-type.png)

   >[!NOTE]
   >
   >有关在登陆页面中使用复选框类型的更多信息，请参阅 [更新多项服务订阅](#multiple-subscriptions) 和 [“协议”复选框](#agreement-checkbox) 中。

1. 如果选择的字段类型与 **[!UICONTROL Field]** 区域，将显示警告消息。 要获得最佳映射，请选择一个适当的值。

   ![](assets/lp_field-type-warning.png)

1. 使用 **[!UICONTROL Field]** 区域，以选择将链接到表单字段的数据库字段。

   ![](assets/lp_select-database-field.png)

   >[!NOTE]
   >
   >登陆页面只能映射 **[!UICONTROL Profiles]** 或 **[!UICONTROL Service]** 资源。

   在本例中，映射 **名称** 的 **[!UICONTROL Last name]** 字段 **[!UICONTROL Profiles]** 资源。

   ![](assets/lp_database-field-example.png)

1. 需要时，可勾选 **[!UICONTROL Mandatory]** 选项。在这种情况下，仅当用户填写了此字段时，才能提交登陆页面。

   ![](assets/lp_mandatory-option.png)

   如果未填写必填字段，则用户提交页面时将显示错误消息。

1. 单击 **[!UICONTROL Confirm]** 以保存更改。

<!--If you choose a mandatory **[!UICONTROL Checkbox]**, make sure that it is of **[!UICONTROL Field]** type.-->

## 数据存储与协调{#data-storage-and-reconciliation}

利用数据协调参数，可定义在用户提交数据后如何管理在登陆页面中输入的数据。

操作步骤：

1. 编辑通过登陆页面仪表板中的 ![](assets/edit_darkgrey-24px.png) 图标访问的登陆页面属性，并显示 **[!UICONTROL Job]** 参数。

   ![](assets/lp_parameters_job.png)

1. 选择 **[!UICONTROL Reconciliation key]**:此数据库字段用于确定访客的配置文件是否在Adobe Campaign数据库中已知。 例如，电子邮件、名字、姓氏。 利用协调键值，可根据 **[!UICONTROL Update strategy]** 参数。

1. 定义 **[!UICONTROL Form parameter mapping]**：利用此部分可映射登陆页面字段参数和协调键值中使用的参数。

1. 选择 **[!UICONTROL Update strategy]**:如果协调键值取回了现有的数据库用户档案，您可以选择使用在表单中输入的数据来更新此用户档案，或者改为阻止此更新。

   ![](assets/lp_parameters_update-strategy.png)

## 多项服务订阅 {#multiple-subscriptions}

您可以在单个登陆页面上使用多个复选框，以允许用户订阅或取消订阅多项服务。

为此请执行以下操作步骤：

1. 设计登陆页面时：

   * 选择一个块，然后从 **[!UICONTROL Form data]** ，选择 **[!UICONTROL Checkbox]** 作为字段类型。

      ![](assets/lp_field-type-checkbox.png)

   * 如果您熟悉HTML，则还可以使用 **[!UICONTROL Show source]** 按钮。

      ![](assets/lp_show_source.png)

      这允许您在页面上的任何方便位置插入复选框。

      ![](assets/lp_manual-checkbox.png)

1. 确保在您的内容中选中该复选框。 的 **[!UICONTROL Type]** 下拉列表显示在 **[!UICONTROL Form data]** 的下一页。 选择 **[!UICONTROL Service and subscription]** 列表。

   ![](assets/lp_service-and-subscription.png)

1. 从 **[!UICONTROL Behavior]** 下拉列表。

   ![](assets/lp_checkbox-behavior.png)

1. 选择 [服务](../../audiences/using/creating-a-service.md) 从对应的列表中。

   ![](assets/lp_checkbox-service.png)

1. 确保 **[!UICONTROL Mandatory]** 选项。 否则，您的用户将别无选择。

   ![](assets/lp_uncheck-mandatory.png)

1. 要添加更多用于订阅其他服务的复选框，请根据需要多次重复上述步骤。

   ![](assets/lp_multiple-checkboxes.png)

发布登陆页面后，用户可以选中多个复选框，以订阅同一页面中的多个新闻稿。

## “协议”复选框 {#agreement-checkbox}

您可以在提交登陆页面之前，添加用户档案需要检查的复选框。

例如，这允许您在用户提交表单之前，请求用户同意隐私政策，或让他们接受您的条款和条件。

>[!IMPORTANT]
>
>对于您的用户而言，必须选中此复选框。 如果未选择，则他们将无法提交登陆页面。

要插入并配置此复选框，请执行以下操作：

1. 设计登陆页面时：

   * 选择一个块，然后从 **[!UICONTROL Form data]** ，选择 **[!UICONTROL Checkbox]** 作为字段类型。

      ![](assets/lp_field-type-checkbox.png)

   * 如果您熟悉HTML，则还可以使用 **[!UICONTROL Show source]** 按钮。

      ![](assets/lp_show_source.png)

      <!--Manually insert a checkbox, such as in the example below:

      <!--Click **[!UICONTROL Hide source]**.-->

1. 确保选中复选框。

   ![](assets/lp_select_checkbox.png)

1. 的 **[!UICONTROL Type]** 下拉列表显示在 **[!UICONTROL Form data]** 的下一页。 选择 **[!UICONTROL Agreement]** 列表。

   ![](assets/lp_form_data_drop-down.png)

   >[!NOTE]
   >
   >的 **[!UICONTROL Agreement]** 元素未映射到Campaign数据库的字段。

1. 单击 ![](assets/lp-properties-icon.png) 图标 **[!UICONTROL Form data]** 以访问复选框“高级属性”。

1. 您可以根据需要编辑消息。

   ![](assets/lp_agreement_message.png)

   如果用户在提交表单之前未选中复选框，则此文本将显示为警告。

   >[!NOTE]
   >
   >默认情况下，此操作是强制操作，无法更改。

1. 单击 **[!UICONTROL Confirm]**。

现在，每次显示登陆页面时，用户都必须在提交表单之前选中此复选框。 如果没有，将显示警告，用户在激活复选框之前将无法提交表单。