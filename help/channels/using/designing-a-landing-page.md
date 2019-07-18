---
title: 设计登陆页面
seo-title: 设计登陆页面
description: 设计登陆页面
seo-description: 按照以下步骤设计登陆页面内容并将其链接到服务。
page-status-flag: 从未激活
uuid: de6fe190-835c-40fd-8101-a809 b430 b423
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 频道
content-type: reference
topic-tags: 登录页面
discoiquuid: bd77d6f0-3143-4030-a91 b-988a beBC534
context-tags: LandingPage，主要
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Designing a landing page{#designing-a-landing-page}

## About content design {#about-content-design}

Landing pages are created as any [marketing activity](../../start/using/marketing-activities.md#about-marketing-activities).

在设计登陆页面时，您需要定义以下内容的内容：

* 页面本身，
* 确认页面，
* 错误页面。

使用操作栏下的切换程序显示和配置每个页面。

这些页面的内容是通过Campaign内容编辑器设计的。Refer to [Design content](../../designing/using/about-landing-page-content-design.md).

## Mapping form fields {#mapping-form-fields}

输入字段用于存储或更新Campaign数据库中的数据。因此，您需要链接数据库字段和输入区域、单选按钮或复选框类型块。要执行此操作，请执行以下操作：

1. 在登陆页面中选择一个块。
1. Complete the **[!UICONTROL Form data]** part in the palette.

   ![](assets/editing_lp_content_4.png)

1. Choose a database field to link with the form field in the **[!UICONTROL Field]** selection zone.

   When the **[!UICONTROL Mandatory]** option is checked, the page can only be submitted if the user has completed this field. 如果必填字段未完成，则用户验证页面时将显示错误消息。

   >[!NOTE]
   >
   >Landing pages can only be mapped with **Profiles**.

1. Define the field type by choosing, for example **[!UICONTROL Text]**, **[!UICONTROL Number]**,or **[!UICONTROL Date]** in the **[!UICONTROL HTML type of the field]** selection area.

>[!NOTE]
>
>内置登录页面的默认字段是预先配置的。您可以根据需要修改它们。

## Submitting the form {#submitting-the-form}

您可以选择访客单击提交按钮时要执行的操作。要执行此操作，请执行以下操作：

1. 选择登陆页面的提交按钮。
1. 在左侧面板的下拉列表中选择操作。Possible actions are: **[!UICONTROL Refresh]** (to refresh the page) and **[!UICONTROL Next page]** (to display the confirmation page).

   ![](assets/editing_lp_content_5.png)

此外，您还可以更改按钮的标签或配置特定链接。要执行此操作，请执行以下操作：

1. 选择提交按钮。
1. Click on the ![](assets/lp_link_properties.png) button in the left panel.
1. 输入按钮的标签，选择链接类型、其属性和目标。

   ![](assets/lp_link_custom.png)

## Linking a form to a service {#linking-a-form-to-a-service}

您可以将表单链接到服务，以便配置文件在验证登录页面时可以订阅特定服务。

链接登陆页面的参数允许您指定执行的操作类型，以及登陆页面是否专门链接到单个服务或其是否为通用服务。

要选择要链接的服务，您需要：

1. Edit the landing page properties accessed via the ![](assets/edit_darkgrey-24px.png) icon in the landing page dashboard, and display the **[!UICONTROL Job]** parameters.

   ![](assets/lp_edit_properties_button.png)

1. Choose **[!UICONTROL Subscription]** in the **[!UICONTROL Specific actions]** drop-down list.

   ![](assets/lp_parameters_5.png)

1. Select **[!UICONTROL Specific service]** to link the landing page to a single service. 如果要将多个服务与登陆页面一起使用，请勿选择此选项。

   Use the **[!UICONTROL Specified service in the URL]** option to allow the landing page to be used for several services. 因此，您必须在配置服务时引用登陆页面。

### Confirm a landing page submission {#confirm-a-landing-page-submission}

当访客提交登陆页面时，您可以配置触发的操作。要执行此操作，请执行以下操作：

1. Edit the landing page properties accessed via the ![](assets/edit_darkgrey-24px.png) icon in the landing page dashboard, and display the **[!UICONTROL Job]** parameters.

   ![](assets/lp_edit_properties_button.png)

1. Under the **[!UICONTROL Specific actions]** section, select **[!UICONTROL Start sending message]** to determine the sending of an automatic message, for example to confirm subscription to a service. 然后，您需要选择电子邮件分发模板。

   请注意，如果已在服务级别配置确认消息，则不应在此屏幕中选择一条确认消息，以避免发送多条确认消息。Refer to [Configure a service](../../audiences/using/creating-a-service.md).

1. Create **[!UICONTROL Additional data]** to enable storing additional data when the landing page is being submitted. 此数据对于访问此页面的用户不可见。只考虑常数值。

   ![](assets/lp_parameters_6.png)

## Setting permissions and pre-loading data {#setting-permissions-and-pre-loading-data}

登录页面的访问权限只能限于识别访客的登录页面，这些访客来自Campaign发送的消息中的链接。在这种情况下，您可以在登录页面预载其数据。要执行此操作，请执行以下操作：

1. Edit the landing page properties accessed via the ![](assets/edit_darkgrey-24px.png) icon in the landing page dashboard, and display the **[!UICONTROL Access & loading]** parameters.

   ![](assets/lp_edit_properties_button.png)

1. Select **[!UICONTROL Preload visitor data]**.

   如果页面的访客与数据库中的配置文件相对应，则其数据将显示在使用数据库数据映射的表单字段中，并考虑登陆页面的个性化元素。

   ![](assets/lp_parameters_3.png)

您还可以：

* Use the URL parameters to identify the visitors, using the **[!UICONTROL Authorize visitor identification via URL parameters]** option: then you must choose the loading key and map the filter parameters with the parameters of the corresponding URL.
* Authorize any visitor to access the landing page, using the **[!UICONTROL Authorize unidentified visitors]** option.

## Setting Google reCAPTCHA {#setting-google-recaptcha}

您可以将Google ReCAPTCHA V与登陆页面设置为保护其免受蠕虫造成的垃圾邮件和滥用。要将其与登陆页面结合使用，您首先需要创建外部帐户。For more information on how to configure it, refer to this [section](../../administration/using/external-accounts.md#google-recaptcha-external-account).

在设置了Google ReactCHA V外部帐户后，您可以将其添加到登陆页面：

1. Before publishing your landing page, access the page properties accessed via the ![](assets/edit_darkgrey-24px.png) icon from you landing page dashboard.

   ![](assets/lp_parameters_google3.png)

1. Unfold the **[!UICONTROL Access & loading]** menu.
1. Check the **[!UICONTROL Use reCAPTCHA to protect your site from spam and abuse]** option.
1. 选择之前创建的Google ReacPTCHA外部帐户。

   ![](assets/lp_parameters_google.png)

1. Click **[!UICONTROL Confirm]**.

您的登陆页面现在可以使用Google ReCAPTCHA设置，它可以在页面底部查看。

![](assets/lp_parameters_google2.png)

Google ReCAPTCHA随后将根据用户与您的页面的交互返回分数。To check your score, connect to your [Google admin console](https://g.co/recaptcha/admin).
