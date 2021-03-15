---
solution: Campaign Standard
product: campaign
title: 共享登陆页面
description: 了解如何测试和发布 Adobe Campaign 登陆页面。
audience: channels
content-type: reference
topic-tags: landing-pages
feature: 登陆页面
role: 业务从业者
level: 中间
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 99%

---


# 测试和发布登陆页面{#testing-publishing--landing-page}

## 关于登陆页面发布{#about-landing-page-publication}

发布登陆页面之前，您需要执行测试：验证执行情况、配置访问权限并设置登陆页面终止服务的时间。这些步骤是先决条件，需要谨慎执行。

## 测试登陆页面{#testing-the-landing-page-}

由于登陆页面将影响您的平台和数据，您需要仔细测试其执行情况。操作步骤：

1. 单击登陆页面操作栏中的 **[!UICONTROL Test]** 按钮。
1. 如果登陆页面需要管理订阅，则从测试屏幕中选择测试用户档案和测试服务。

   ![](assets/lp_test_2.png)

1. 在相应的字段中输入数据，然后选择相应的选项。
1. 提交登陆页面并检查数据库中的更新。

   >[!IMPORTANT]
   >
   >提交表单后，使用的服务和用户档案都会更新。

1. 使用各种用户档案和数据重复此操作。

您也可从此屏幕生成登陆页面缩览图。

>[!NOTE]
>
>要在 Campaign 用户界面中显示登陆页面预览，应用程序服务器 URL 必须是安全的。在本例中，[配置品牌](../../administration/using/branding.md#configuring-and-using-brands)时，请使用 https:// 而不是 http:// 设置此 URL。

## 设置有效性参数{#setting-up-validity-parameters}

在发布之前，出于安全原因和平台性能的考虑，我们强烈建议您在登陆页面属性中设置过期日期。达到选定日期时，登陆页面将自动取消发布。操作步骤：

1. 编辑通过登陆页仪表板中的 ![](assets/edit_darkgrey-24px.png) 按钮访问的登陆页面属性。

   ![](assets/lp_edit_properties_button.png)

1. 在 **[!UICONTROL Publication]** 部分中设置过期日期和时间：登陆页面将在指定的该日期自动取消发布，不再可用。

   您可以为此日期和时间选择时区。

1. 定义重定向 URL，以在访客尝试访问不活动的登陆页面时对访客进行重定向。

   ![](assets/lp_settings_general.png)

>[!IMPORTANT]
>
>您还可以定义部署日期和时间：随后登陆页面将在指定的日期自动发布。

## 发布登陆页面{#publishing-a-landing-page}

发布登陆页面后，登陆页面就会上线并可被访客访问。

您可以随时通过 **[!UICONTROL Publish]** 按钮取消发布或更新并重新发布登陆页面。但是，如果重新发布失败且尚未取消发布登陆页面，则更新之前的版本将保持上线状态。
