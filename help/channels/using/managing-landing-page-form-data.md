---
solution: Campaign Standard
product: campaign
title: 管理登陆页面表单数据
description: 了解如何管理登陆页面表单数据。
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,main
feature: 登陆页面
role: User
level: Intermediate
exl-id: 7083447c-4cac-41cb-8453-369819e0c7c1
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 62%

---

# 管理登陆页面表单数据{#managing-landing-page-form-data}

## 更改登陆页面表单数据属性{#changing-a-landing-page-form-data-properties}

您可以将数据库字段链接到输入区、单选按钮或复选框类型块。为此，请选择块并访问面板中的&#x200B;**[!UICONTROL Form data]**。

![](assets/delivery_content_9.png)

* 利用“**字段**”输入区域，您可以选择要与表单字段链接的数据库字段。
* 利用“**必填**”选项，可设置为仅在用户填写字段后才授权页面提交。如果未填写必填字段，则会显示错误消息。

## 映射表单字段 {#mapping-form-fields}

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

## “协议”复选框 {#agreement-checkbox}

您可以在提交登陆页面之前，添加用户档案需要检查的复选框。

例如，这允许您在用户提交表单之前，请求用户同意隐私政策，或让他们接受您的条款和条件。

<!--This is particularly useful in the following case:

When a profile opens the landing page from an Outlook.com mailbox, Outlook checks whether the links on the landing page are suspicious. However, this Outlook security feature (called safelinks) has an unwanted effect: it automatically activates the buttons included on the landing page. Consequently, profiles are automatically subscribed or unsubscribed without confirmation when the landing page is displayed after clicking the email link, even if they do not submit the form.

![](assets/lp_submit_button.png)

To avoid this, Adobe recommends you always add to your landing page a checkbox which enables the profile to agree before proceeding with subscription or unsubscription.-->

>[!IMPORTANT]
>
>对于您的用户而言，必须选中此复选框。 如果未选择，则他们将无法提交登陆页面。

要插入并配置此复选框，请执行以下操作：

1. 设计登陆页面时，单击&#x200B;**[!UICONTROL Show source]**。

   ![](assets/lp_show_source.png)

1. 手动插入复选框，如以下示例中所示：

   ![](assets/lp_checkbox_code.png)

   <!--
   <div id="HtmlPage_htmlPage.line3" data-nl-format="datetime"><input type="checkbox" class="nl-dce-todo" data-nl-bindto="agreement" data-nl-agreementmsg="You must agree with the terms and conditions before proceeding" />I agree with the terms and conditions</div>
   -->

1. 单击 **[!UICONTROL Hide source]**。

1. 随即会显示新复选框。 选择它。

   ![](assets/lp_select_checkbox.png)

1. 相应的下拉列表显示在面板的&#x200B;**[!UICONTROL Form data]**&#x200B;部分中。 从列表中选择&#x200B;**[!UICONTROL Agreement]**。

   ![](assets/lp_form_data_drop-down.png)

   >[!NOTE]
   >
   >**[!UICONTROL Agreement]**&#x200B;元素未映射到Campaign数据库的字段。

1. 单击&#x200B;**[!UICONTROL Form data]**&#x200B;旁边的![](assets/lp-properties-icon.png)图标以访问复选框高级属性。

1. 您可以根据需要编辑消息。

   ![](assets/lp_agreement_message.png)

   如果用户在提交表单之前未选中复选框，则此文本将显示为警告。

   >[!NOTE]
   >
   >默认情况下，此操作是强制操作，无法更改。

1. 单击 **[!UICONTROL Confirm]**。

现在，每次显示登陆页面时，用户都必须在提交表单之前选中此复选框。 如果没有，将显示警告，用户在激活复选框之前将无法提交表单。