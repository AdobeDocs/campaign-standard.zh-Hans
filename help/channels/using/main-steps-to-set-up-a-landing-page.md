---
title: 设置登陆页面的主要步骤
seo-title: 设置登陆页面的主要步骤
description: 设置登陆页面的主要步骤
seo-description: 了解设置登陆页面的主要步骤
page-status-flag: 从未激活
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: 勒梅特
products: SG_CAMPAIGN/STANDARD
audience: 频道
content-type: 参考
topic-tags: 登陆页面
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage，向导；landingPage，概述；landingPage，主页
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1f100f6b041c6dbb298113b4ecc7830951714131

---


# 设置登陆页面的主要步骤 {#main-steps-create-a-landing-page}

## 关于登陆页面创建

设置登陆页面时的主要步骤如下：

![](assets/lp_steps.png)

在本页中，您将找到有关这些步骤中每个步骤的信息，以及对专用文档的引用，以了解更多详细信息。

## 配置登陆页面模板 {#configure-the-landing-page-template}

在设置登陆页面之前，第一步是配置与您的需求对应的登陆页面模板。 模板准备就绪后，所有基于该模板的登录页面都将预先配置所需的参数。

1. 从高级菜单中，通过Adobe Campaign徽标，选 **[!UICONTROL Resources]** 择/ **[!UICONTROL Templates]** / **[!UICONTROL Landing page templates]**，然后复制要使用的模板。
1. 在模板属性中，指定登录页面必须具有的所有公用参数。 例如：定位维度、已识别或未识别访客的页面访问参数、访客对表单验证的特定操作、内容中使用的品牌／徽标等。
1. 保存修改。

有关登录页面模板的详细信息，请参 [阅此部分](../../channels/using/about-landing-pages.md)。

![](assets/lp-steps1.png)

## 创建和配置登陆页面 {#create-and-configure-the-landing-page}

从上一步中定义的模板，在计划或营销活动中创建新的登录页面。

1. 根据所需的模板创建登陆页面。
1. 输入登录页面的常规参数（标签、说明等）。
1. 然后，您将访问登陆页面功能板。 根据需要编辑登陆页面属性。 默认情况下，这些属性是在登陆页面模板中配置的属性。
出于安全原因和平台性能的考虑，我们强烈建议您在登录页面属性中设置到期日期。 完成后，登录页面将在选定日期自动取消发布。 For more on validity parameters, refer to [this section](../../channels/using/sharing-a-landing-page.md#setting-up-validity-parameters).

   ![](assets/lp-steps3.png)

   >[!NOTE]
   >
   >您的修改仅对正在编辑的登录页面有效。 如果要将这些修改应用到其他登录页面，您可以在专用模板中执行这些修改，然后从该模板创建其他登录页面。

## 设计登陆页面 {#design-the-landing-page}

您现在可以定义登陆页面的内容。 默认情况下，登录页面包含三个可通过滚动箭头访问的页面：主内容页、确认页和错误页。

![](assets/lp-steps4.png)

默认情况下，每个页面上都配置了多个字段。 如有必要，您可以编辑其属性和映射。

您还可以配置在配置文件单击确认按钮后其行为方式，并根据您的需求（图像、个性化字段等）个性化内容。 例如，您可以在登录页面的确认页面上插入配置文件的名，以感谢他们注册。

有关登录页面设计的详细信息，请参 [阅此部分](../../channels/using/designing-a-landing-page.md)。

## 测试登陆页面 {#test-the-landing-page}

定义登陆页面后，您可以模拟登陆页面在线可用时的执行和行为方式。

![](assets/lp-steps5.png)

>[!CAUTION]
>
>登录页面测试只能用配置文件进行，而不能用测试配置文件进行。 提交表单时，所选配置文件的数据将实际更新。 要避免修改真实的客户档案，请使用虚假的客户档案。

如果您对登录页面的行为方式感到满意，则可以发布它以使其联机可用。

有关如何测试登陆页面的详细信息，请参阅 [此部分](../../channels/using/sharing-a-landing-page.md#testing-the-landing-page-)。

## 发布登陆页面 {#publish-the-landing-page}

测试成功后，您可以使用功能板中操作栏 **[!UICONTROL Publish]** 中的按钮发布登录页面。 监视块显示发布的进度和状态。

发布登录页面后，即可在线访问该页面。 发布后，您始终可以更新它：为此，您必须在每次修改后重新发布它。 您还可以随时取消发布登录页面，以便不再可用。

![](assets/lp-steps6.png)

发布后，您的登录页面即可供使用。 然后，您可以设置不同的机制，以便访问该机制以在数据库中获取新配置文件或获取有关现有配置文件的其他信息。

有关登录页面发布的详细信息，请参 [阅此部分](../../channels/using/sharing-a-landing-page.md#publishing-a-landing-page)。
