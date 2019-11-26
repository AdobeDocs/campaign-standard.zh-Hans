---
title: 配置登陆页面
description: 了解如何配置登陆页面的属性。
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
source-git-commit: 95e01eb33097fc76caac3f4dd5f5591461b887cf

---


# 配置登陆页面 {#configuring-landing-page}

## 确认登陆页面提交 {#confirm-a-landing-page-submission}

当访客提交登陆页面时，您可以配置触发的操作。 操作步骤：

1. 编辑通过登陆页面功能板中的图 ![](assets/edit_darkgrey-24px.png) 标访问的登陆页面属性，并显示参 **[!UICONTROL Job]** 数。

   ![](assets/lp_edit_properties_button.png)

1. 在部分 **[!UICONTROL Specific actions]** 下，选择以 **[!UICONTROL Start sending message]** 确定自动消息的发送，例如确认订阅服务。 然后，您需要选择电子邮件分发模板。

   请注意，如果在服务级别上已配置确认消息，则不应在此屏幕中选择一条以避免发送多条确认消息。 请参阅 [配置服务](../../audiences/using/creating-a-service.md)。

1. 创建 **[!UICONTROL Additional data]** 该组件可在提交登录页面时存储其他数据。 此数据对访问该页面的用户不可见。 只考虑常数值。

   ![](assets/lp_parameters_6.png)

## 将登陆页面链接到服务 {#linking-a-landing-page-to-a-service}

您可以将表单链接到服务，以便配置文件在验证登陆页面时可以订阅特定服务。

通过用于链接登陆页面的参数，您可以指定执行的操作类型以及登陆页面是专门链接到单个服务还是通用。

要选择要链接的服务，您需要：

1. 编辑通过登陆页面功能板中的图 ![](assets/edit_darkgrey-24px.png) 标访问的登陆页面属性，并显示参 **[!UICONTROL Job]** 数。

   ![](assets/lp_edit_properties_button.png)

1. 在下 **[!UICONTROL Subscription]** 拉列 **[!UICONTROL Specific actions]** 表中选择。

   ![](assets/lp_parameters_5.png)

1. 选择 **[!UICONTROL Specific service]** 以将登陆页面链接到单个服务。 如果要对登录页面使用多项服务，请勿选择此选项。

   使用 **[!UICONTROL Specified service in the URL]** 此选项可允许登录页面用于多项服务。 因此，在配置服务时必须引用登陆页面。

## 设置权限和预加载数据 {#setting-permissions-and-pre-loading-data}

登录页面的访问权限可限于已识别的访客（例如，来自营销活动发送的消息中的链接）或特定组织单位的访客。
对于已识别的访客，您可以在登录页面中预加载其数据。 操作步骤：

1. 编辑通过登陆页面功能板中的图 ![](assets/edit_darkgrey-24px.png) 标访问的登陆页面属性，并显示参 **[!UICONTROL Access & loading]** 数。

   ![](assets/lp_edit_properties_button.png)

1. Select **[!UICONTROL Preload visitor data]**.

   如果页面的访客与数据库中的配置文件相对应，则其数据将显示在与数据库数据映射的表单字段中，并会考虑登录页面的个性化元素。

   ![](assets/lp_parameters_3.png)

您还可以：

* 使用URL参数，使用以下选项识别访 **[!UICONTROL Authorize visitor identification via URL parameters]** 客：然后，必须选择加载键，并将过滤器参数与相应URL的参数映射。
* 使用此选项授权任何访客访问登 **[!UICONTROL Authorize unidentified visitors]** 录页。

登录页面也可以链接到组织单元。 这将定义用户对不同登录页面的访问权限。 要分配组织单位，请执行以下操作：

1. 通过图标访问登录页面 **[!UICONTROL Edit properties]** 属性。

   ![](assets/lp_parameters_google3.png)

1. 打开 **[!UICONTROL Access authorization]**。

1. 单击下拉菜单并选择您的组织单位。 有关如何创建组织单位的详细信息，请参阅此 [页](../../administration/using/organizational-units.md)。

   ![](assets/lp_org_unit_2.png)

1. 自 **[!UICONTROL Created by]**&#x200B;动完 **[!UICONTROL Created]**&#x200B;成、 **[!UICONTROL Access authorization]** 和 **[!UICONTROL Last modified]** 字段。

1. 然后， **[!UICONTROL Confirm]** 单击 **[!UICONTROL Save]**。

登录页面现在只能由选定组织单位内的用户访问和管理。

![](assets/lp_org_unit_3.png)

## 设置Google reCAPTCHA {#setting-google-recaptcha}

您可以使用登录页面设置Google reCAPTCHA V3，以保护其免受由机器人程序造成的垃圾邮件和滥用。 要将其用于登陆页面，您首先需要创建一个外部帐户。 有关如何配置它的详细信息，请参阅此 [部分](../../administration/using/external-accounts.md#google-recaptcha-external-account)。

设置Google reCAPTCHA V3外部帐户后，可将其添加到登录页面：

1. 在发布登录页面之前，访问通过登录页面功能板中 ![](assets/edit_darkgrey-24px.png) 的图标访问的页面属性。

   ![](assets/lp_parameters_google3.png)

1. 打开菜 **[!UICONTROL Access & loading]** 单。
1. 选中该 **[!UICONTROL Use reCAPTCHA to protect your site from spam and abuse]** 选项。
1. 选择您之前创建的Google reCAPTCHA外部帐户。

   ![](assets/lp_parameters_google.png)

1. Click **[!UICONTROL Confirm]**.

登录页面现已通过Google reCAPTCHA设置，可在页面底部查看。

![](assets/lp_parameters_google2.png)

然后，Google reCAPTCHA将根据用户与您页面的交互情况返回得分。 要检查得分，请连接到您的 [Google管理控制台](https://g.co/recaptcha/admin)。
