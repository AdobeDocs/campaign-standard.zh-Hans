---
title: 共享登陆页面
seo-title: 共享登陆页面
description: 共享登陆页面
seo-description: 了解如何在Adobe Campaign中测试和发布登陆页面。
page-status-flag: 从未激活
uuid: fb7b087a-3292-496c-bc41-2e3012 bacf59
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 频道
content-type: reference
topic-tags: 登录页面
discoiquuid: f7d4bb71-f957-4f86-97c7-8ac0 a0030026
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Sharing a landing page{#sharing-a-landing-page}

## About landing page publication {#about-landing-page-publication}

在发布登陆页面之前，您需要执行测试：验证执行，配置访问页面并设置登陆页面生命周期。这些步骤是先决条件，需要谨慎执行。

## Testing the landing page {#testing-the-landing-page-}

由于登陆页面会影响平台和数据，因此您需要仔细测试执行情况。要执行此操作，请执行以下操作：

1. Click the **[!UICONTROL Test]** button in the action bar of the landing page.
1. 在测试屏幕中，选择测试配置文件，然后选择测试服务(如果登陆页面用于管理订阅)。

   ![](assets/lp_test_2.png)

1. 在字段中输入数据，并选择选项。
1. 提交登陆页面并检查数据库中的更新。

   >[!CAUTION]
   >
   >提交表单后，将更新使用的服务和配置文件。

1. 使用各种档案和数据重复此操作。

   您还可以从此屏幕生成登陆页面缩略图。

## Setting up validity parameters {#setting-up-validity-parameters}

在发布之前，出于安全原因和平台性能，我们强烈建议您在登录页面属性中设置过期日期。在选定的日期，登录页面会自动取消发布。要执行此操作，请执行以下操作：

1. Edit the landing page properties accessed via the ![](assets/edit_darkgrey-24px.png) button in the landing page dashboard.

   ![](assets/lp_edit_properties_button.png)

1. Set up expiration date and time in the **[!UICONTROL Publication]** section: the landing page will automatically be unpublished on the specified date and therefore no longer be available.

   您可以选择要考虑的日期和时间的时区。

1. 定义重定向URL以在尝试访问非活动登录页面时重定向访客。

   ![](assets/lp_settings_general.png)

>[!CAUTION]
>
>您还可以定义部署日期和时间：登录页面随后将在指定的日期自动发布。

## Publishing a landing page {#publishing-a-landing-page}

当您发布登陆页面时，该页面上线并可由访客访问。

You can unpublish or update and republish your landing page at any time, via the **[!UICONTROL Publish]** button. 但是，如果重新发布失败且您尚未取消发布登陆页面，则第一个版本仍将保持联机状态。
