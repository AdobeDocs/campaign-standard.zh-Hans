---
title: 品牌
description: 发现管理品牌标识的所有可用工具。
page-status-flag: never-activated
uuid: d66ac5a2-2ae1-4870-b48e-7f276744ffdd
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: application-settings
discoiquuid: cbb1dcec-3bc6-4013-87fa-27d0e5d32bf8
context-tags: branding,overview;branding,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e18407ab4bf70caa417b16bbc645fd2c6ba1818b

---


# 品牌{#branding}

## 关于品牌标识 {#about-brand-identity}

每个公司都有品牌视觉和技术指导。 通过Adobe Campaign，您可以定义一套规范，从徽标到技术方面（如电子邮件发送者、URL或域），为客户提供一致的品牌。

技术管理员可以定义一个或多个品牌以集中输入影响品牌标识的参数。 这包括品牌徽标、登陆页访问URL的域或消息跟踪设置。 通过Adobe Campaign，您可以创建这些品牌并将它们链接到消息或登陆页。 此配置在模板中进行管理。

## 配置和使用品牌 {#configuring-and-using-brands}

配置和使用品牌的主要原则是：

1. 创建和配置品牌——此操作需要特定权限，并由Adobe Campaign技术管理员执行。
1. 为此品牌创建一个或多个投放和登陆页模板。 请参阅创 [建模板](../../start/using/marketing-activity-templates.md) 。
1. 根据此模板创建消息和登陆页。 请参阅创 [建电子邮件](../../channels/using/creating-an-email.md)[和创建登陆页](../../channels/using/designing-a-landing-page.md) 。

>[!IMPORTANT]
>
>不能由最终用户创建或修改品牌： 这些操作必须由Adobe Campaign技术管理员执行。 如需任何请求，请与Adobe客户关怀部门联系。
>
>不能在事务消息的上下文中使用多品牌。 有关此方面的更多信息，请参 [阅事务性消息和品牌](../../channels/using/about-transactional-messaging.md#permissions-and-branding)。

品牌可在菜单中找 **[!UICONTROL Administration > Instance settings > Brand configuration]** 到。

默认情况下，新创建的品牌仅对管理员分配了相应权限的用户可见。

品牌 **由** 以下特征定义：

* 一种 **身份**，用于定义和个性化您的品牌。 此部分包含以下字段：

   ![](assets/branding_01.png)

   * **界面中** ，显示标签
   * **品牌名称**
   * **网站URL** 和 **品牌的网站** 标签
   * **品牌徽标**

* **[!UICONTROL Header parameters of sent emails]** 个性化活动将看到的内容。 此部分包含以下字段：

   ![](assets/branding_04_header.png)

   * **发件人(电子邮件地址** )与品牌的电子邮件地址。
   * **发件人** （姓名）。
   * **使用客户可以回复的电子邮件地址** （电子邮件地址）回复。
   * **使用品牌名称** ，回复到（名称）。
   * **错误(电子邮件地址** )，电子邮件地址用于发生错误时。
   >[!IMPORTANT]
   >
   >更新了电子邮件的标题参数后，如果发件人的姓名和电子邮件地址在从模板创建的电子邮件中没有更改，请检查模板的高级设置。

* **Internet上公开的服务器定义用于跟踪** 、也用于登陆页访问的服务器。 此部分包含以下字段：

   ![](assets/configure_branding_04.png)

   * **用于托管和访问您创建的不同登陆页** 的应用程序服务器的外部URL。
   * **在投放期间用作跟踪** URL的跟踪服务器的外部URL。
   * **镜像页面服务器的外部URL** ，用作投放中的默认镜像页面。
   >[!NOTE]
   >
   >要在登陆页用户界面中显示预览和镜像页面呈现，应用服务器和镜像页面服务器URL必须是安全的。 在这种情况下，在设置这些URL时，请使用https://，而不是http://。

* **[!UICONTROL Tracking URL configuration (Web Analytics)]**，它定义品牌的URL跟踪配置。

   此处定义了允许在外部系统（如Web分析工具，如Adobe Analytics或Google Analytics）上跟踪链接的其他参数。

   ![](assets/branding_05.png)

## 为电子邮件分配品牌 {#assigning-a-brand-to-an-email}

### 将品牌关联到模板 {#linking-a-brand-to-a-template}

要使用为品牌定义的参数，必须将其链接到投放模板或登陆页模板。 为此，您必须创建或编辑模板。

>[!NOTE]
>
>有关创建模板的详细信息，请参阅创 [建模板部分](../../start/using/marketing-activity-templates.md) 。

创建模板后，您可以将其链接到品牌。 操作步骤：

1. 单击该 **[!UICONTROL Edit properties]** 按钮可访问模板属性。

   ![](assets/branding_04.png)

1. 使用下拉列表选择要链接到模板的品牌。

   >[!NOTE]
   >
   >默认情况下，将 **[!UICONTROL Default brand (branding)]** 选中该选项。

   ![](assets/branding_05.png)

   要视图所选品牌的配置方式，请单击 **[!UICONTROL Navigate to the detail of the element selected]** 图标。

   ![](assets/branding_06.png)

1. 确认您的选择并保存您的模板。

您的模板已链接到品牌。 在电子邮件编辑器中，默认发件人 **的电子邮件地址**、 **默认发件人姓名**&#x200B;或徽标等元 **** 素将使用配置的品牌数据。

### 品牌使用案例 {#branding-use-case}

在此示例中，我们将创建一个与旅行相关的新品牌，并在电子邮件中使用它。

#### 配置新品牌 {#configure-a-new-brand}

>[!IMPORTANT]
>
>品牌配置仅在需要特定权限和技术设置时由Adobe管理。

1. Adobe Campaign管理员在中创建品牌 **[!UICONTROL Administration > Instance settings > Brand configuration]**。 他从高级 **菜单中添加** “热带度假”元素，并 **[!UICONTROL ID]** 配置品牌 **[!UICONTROL Header parameters of sent emails]** 和品牌。

   ![](assets/branding_07.png)

1. 然后，管理员配置Internet上 **公开的服务器的URL** ，以便使用登陆页，然后配置跟踪URL。

   在此示例中，使 **用的Web** Analytics工 **具是Google Analytics**。 管理员按如下方式配置跟踪URL:

   ![](assets/branding_12.png)

品牌创建和配置正确。 现在，营销团队可以使用它。

#### 实施新品牌 {#implement-a-new-brand}

作为投放经理，您负责创建投放模板以使用新品牌。 为此，请按照以下步骤操作：

1. 在高级菜单 **[!UICONTROL Resources > Templates > Delivery templates]**&#x200B;中，重复内置模板以配置新投放模板。

   ![](assets/branding_08.png)

1. 要将此模板链接到 **热带度假品牌** ，请编辑模板属性并从下拉列表中选择品牌。

   ![](assets/branding_09.png)

1. 配置此电子邮件模板以反映品牌标识。
1. 模板完成后，您可以保存它。

   ![](assets/branding_10.png)

   该投放模板现在可用于创建将发送给受众的电子邮件。

#### 在投放中使用新品牌 {#use-the-new-brand-in-a-delivery}

要创建链接到品牌的电子邮件，请按照以下步骤操作：

1. 单击菜 **[!UICONTROL Create]** 单中的按 **[!UICONTROL Marketing activities]** 钮。

   ![](assets/branding_14.png)

1. 选择 **[!UICONTROL Email]** 活动，然后选择链接到新品牌的模板。

   ![](assets/branding_15.png)

1. 您的电子邮件已配置。 您可以使用测试用户档案在测试信息之前检查信息，然后将其发送给受众。

   ![](assets/branding_16.png)

