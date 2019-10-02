---
title: 设计登陆页面
seo-title: 设计登陆页面
description: 设计登陆页面
seo-description: 按照以下步骤设计登录页面的内容并将其链接到服务。
page-status-flag: 从未激活
uuid: de6fe190-835c-40fd-8101-a809b430b423
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 频道
content-type: 参考
topic-tags: 登陆页面
discoiquuid: bd77d6f0-3143-4030-a91b-988a2bebc534
context-tags: landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aeb0e7bc6765b23042fafd34fb360d4e3046adcd

---


# 设计登陆页面{#designing-a-landing-page}

## 关于内容设计 {#about-content-design}

登录页面以任何营销活动 [的形式创建](../../start/using/marketing-activities.md#about-marketing-activities)。

在设计登陆页面时，您需要定义以下内容：

* 页面本身，
* 确认页面，
* 错误页面。

使用操作栏下的切换器显示和配置每个页面。

这些页面的内容通过Campaign内容编辑器进行设计。 请参阅 [设计内容](../../channels/using/about-landing-page-content-design.md)。

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

## 提交表单 {#submitting-the-form}

您可以选择访客单击提交按钮时要执行的操作。 操作步骤：

1. 选择登陆页面的提交按钮。
1. 在左侧面板的下拉列表中选择操作。 可能的操作包括：( **[!UICONTROL Refresh]** 刷新页面)和 **[!UICONTROL Next page]** （显示确认页面）。

   ![](assets/editing_lp_content_5.png)

此外，您还可以更改按钮的标签或配置特定链接。 操作步骤：

1. 选择提交按钮。
1. 单击左 ![](assets/lp_link_properties.png) 侧面板中的按钮。
1. 输入按钮的标签，选择链接类型、其属性和目标。

   ![](assets/lp_link_custom.png)

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

### 确认登陆页面提交 {#confirm-a-landing-page-submission}

当访客提交登陆页面时，您可以配置触发的操作。 操作步骤：

1. 编辑通过登陆页面功能板中的图 ![](assets/edit_darkgrey-24px.png) 标访问的登陆页面属性，并显示参 **[!UICONTROL Job]** 数。

   ![](assets/lp_edit_properties_button.png)

1. 在部分 **[!UICONTROL Specific actions]** 下，选择以 **[!UICONTROL Start sending message]** 确定自动消息的发送，例如确认订阅服务。 然后，您需要选择电子邮件分发模板。

   请注意，如果在服务级别上已配置确认消息，则不应在此屏幕中选择一条以避免发送多条确认消息。 请参阅 [配置服务](../../audiences/using/creating-a-service.md)。

1. 创建 **[!UICONTROL Additional data]** 该组件可在提交登录页面时存储其他数据。 此数据对访问该页面的用户不可见。 只考虑常数值。

   ![](assets/lp_parameters_6.png)

## 设置权限和预加载数据 {#setting-permissions-and-pre-loading-data}

登录页面的访问权限可限于已识别的访客，例如，这些访客来自营销活动发送的消息中的链接。 在这种情况下，您可以在登录页面中预加载其数据。 操作步骤：

1. 编辑通过登陆页面功能板中的图 ![](assets/edit_darkgrey-24px.png) 标访问的登陆页面属性，并显示参 **[!UICONTROL Access & loading]** 数。

   ![](assets/lp_edit_properties_button.png)

1. Select **[!UICONTROL Preload visitor data]**.

   如果页面的访客与数据库中的配置文件相对应，则其数据将显示在与数据库数据映射的表单字段中，并会考虑登录页面的个性化元素。

   ![](assets/lp_parameters_3.png)

您还可以：

* 使用URL参数，使用以下选项识别访 **[!UICONTROL Authorize visitor identification via URL parameters]** 客：然后，必须选择加载键，并将过滤器参数与相应URL的参数映射。
* 使用此选项授权任何访客访问登 **[!UICONTROL Authorize unidentified visitors]** 录页。

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
