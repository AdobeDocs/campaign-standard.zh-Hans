---
title: 共享登陆页面
description: 了解如何在Adobe Campaign中测试和发布登录页面。
page-status-flag: never-activated
uuid: fb7b087a-3292-496c-bc41-2e3012bacf59
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: f7d4bb71-f957-4f86-97c7-8ac0a0030026
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aa92475c1f8b37f995ebdc74c4a1f43692a53c21

---


# 测试和发布登陆页面{#testing-publishing--landing-page}

## 关于登录页面发布 {#about-landing-page-publication}

在发布登陆页面之前，您需要执行以下测试：验证执行、配置访问权限并设置登录页面的终止时间。 这些步骤是先决条件，需要谨慎执行。

## 测试登陆页面 {#testing-the-landing-page-}

由于登陆页面将影响您的平台和数据，您需要仔细测试其执行情况。 操作步骤：

1. 单击登 **[!UICONTROL Test]**录页面操作栏中的按钮。
1. 从测试屏幕中，如果登录页面要管理订阅，请选择测试配置文件和测试服务。

   ![](assets/lp_test_2.png)

1. 在字段中输入数据，然后选择选项。
1. 提交登陆页面并检查数据库中的更新。

   >[!IMPORTANT]
   >
   >提交表单后，使用的服务和配置文件会更新。

1. 使用各种配置文件和数据重复此操作。

   您还可以从此屏幕生成登陆页面缩略图。

>[!NOTE]
>
>如果应用程序服务器URL不安全(即，如果不以https://开头)，则无法从营销活动用户界面中显示登录页面预览。 此服务器在配置品牌时 [进行定义](../../administration/using/branding.md#configuring-and-using-brands)。

## 设置有效性参数 {#setting-up-validity-parameters}

在发布之前，出于安全原因和平台性能原因，我们强烈建议您在登录页面属性中设置到期日期。 在选定日期，登录页面将自动取消发布。 操作步骤：

1. 编辑通过登陆页面功能板中的 ![](assets/edit_darkgrey-24px.png) 按钮访问的登陆页面属性。

   ![](assets/lp_edit_properties_button.png)

1. 在部分中设置到期日期和 **[!UICONTROL Publication]**时间：登陆页面将在指定的日期自动取消发布，因此不再可用。

   您可以选择要考虑此日期和时间的时区。

1. 定义重定向URL，以在尝试访问非活动登录页面时重定向访客。

   ![](assets/lp_settings_general.png)

>[!IMPORTANT]
>
>您还可以定义部署日期和时间：然后，登陆页面将在指定日期自动发布。

## 发布登陆页面 {#publishing-a-landing-page}

当您发布登陆页面时，该页面将开始生效，访客可以访问它。

您可以随时通过按钮取消发布或更新并重新发布登陆 **[!UICONTROL Publish]**页面。 但是，如果重新发布失败且尚未取消发布登录页面，则第一个版本将保持联机状态。
