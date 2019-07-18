---
title: 在Campaign中管理选择加入和退出
seo-title: 在Campaign中管理选择加入和退出
description: 在Campaign中管理选择加入和退出
seo-description: 了解如何在Adobe Campaign中管理参与和选择退出。
page-status-flag: 从未激活
uuid: a1801ec-562b-420e-8d79-c07 d066 b7 b1 a
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 受众
content-type: reference
topic-tags: 了解退出和选择退出流程
discoiquuid: 6b5680f2-bba9-453e-a0 d5-8ca69 dd02001
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Managing opt-in and opt-out in Campaign{#managing-opt-in-and-opt-out-in-campaign}

## Managing opt-in and opt-out from a profile {#managing-opt-in-and-opt-out-from-a-profile}

Users can be opted in or out by an operator directly from the profile **[!UICONTROL General]** tab.

**[!UICONTROL No longer contact (blacklist)]** 在部分中，选定的复选框对应于用户选择退出的渠道。根据用户的需求选择渠道。

![](assets/optin_landingpage_3.png)

## Setting up opt-in and opt-out landing pages {#setting-up-opt-in-and-opt-out-landing-pages}

To give users the ability to opt in or opt out, you have to create and publish a **[!UICONTROL Profile acquisition]** landing page. 然后，他们可以根据需要选择渠道。为此，请按照以下步骤操作。

You can also set up a **[!UICONTROL BlackList]** landing page that will enable users to opt out from all deliveries. For more on this, refer to [Setting up a landing page to opt out from all deliveries](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-a-landing-page-to-opt-out-from-all-deliveries).

>[!NOTE]
>
>登录页面还可用于启用服务订阅。For more on this, refer to [this page](../../channels/using/designing-a-landing-page.md#linking-a-form-to-a-service).

1. Create a **[!UICONTROL Profile acquisition]** landing page (see [this section](../../channels/using/about-landing-pages.md)).
1. 在每个所需渠道的登陆页面内容中添加一个复选框，然后将其链接到营销活动数据库中的相应字段。

   ![](assets/optin_landingpage_1.png)

1. 保存登陆页面并将其发布。
1. In the landing page, the checkboxes are already selected according to the profile **[!UICONTROL General]** tab. 用户可以根据自己的需求选择或取消选择渠道，并提交表单。

   ![](assets/optin_landingpage_2.png)

1. Once the form submitted, the profile **[!UICONTROL General]** tab is updated according to the user's selection.

   ![](assets/optin_landingpage_3.png)

### Setting up a landing page to opt out from all deliveries {#setting-up-a-landing-page-to-opt-out-from-all-deliveries}

To give users the ability to opt out from all deliveries, you have to create and publish a **[!UICONTROL BlackList]** landing page. For more on landing pages creation, refer to [this page](../../channels/using/about-landing-pages.md).

Once a user clicks on the landing page link, the **[!UICONTROL No longer contact (by any channel)]** option in the profile is automatically selected.

![](assets/blacklisting_allchannels.png)

