---
title: 管理 Campaign 中的选择启用和选择禁用
description: 了解如何在Adobe Campaign中管理选择加入和选择退出。
page-status-flag: never-activated
uuid: aa1801ec-562b-420e-8d79-c07d066b7b1a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
discoiquuid: 6b5680f2-bba9-453e-a0d5-8ca69dd02001
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 95e01eb33097fc76caac3f4dd5f5591461b887cf

---


# 管理 Campaign 中的选择启用和选择禁用{#managing-opt-in-and-opt-out-in-campaign}

## 从配置文件管理选择加入和选择退出 {#managing-opt-in-and-opt-out-from-a-profile}

操作员可以直接从配置文件选项卡中选择加入或退出 **[!UICONTROL General]** 用户。

在部 **[!UICONTROL No longer contact (blacklist)]** 分中，选定的复选框与用户选择退出的渠道相对应。 根据用户的需求选择渠道。

![](assets/optin_landingpage_3.png)

## 设置选择加入和选择退出登录页面 {#setting-up-opt-in-and-opt-out-landing-pages}

要允许用户选择加入或选择退出，您必须创建并发布登 **[!UICONTROL Profile acquisition]** 录页面。 然后，他们可以根据自己的需求选择渠道。 为此，请按照以下步骤操作。

您还可以设置登录页 **[!UICONTROL BlackList]** 面，以使用户能够退出所有分发。 有关详细信息，请参 [阅设置登录页面以退出所有交付](#setting-up-a-landing-page-to-opt-out-from-all-deliveries)。

>[!NOTE]
>
>登录页面还可用于启用服务订阅。 有关详细信息，请参见[此页面](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service)。

1. 创建登 **[!UICONTROL Profile acquisition]** 陆页面(请参 [阅此部分](../../channels/using/getting-started-with-landing-pages.md))。
1. 在每个所需渠道的登录页面内容中添加一个复选框，然后将其链接到Campaign数据库中的相应字段。

   ![](assets/optin_landingpage_1.png)

1. 保存登陆页面并发布它。
1. 在登录页面中，已根据配置文件选项卡选择复选 **[!UICONTROL General]** 框。 用户可以根据自己的需要选择或取消选择渠道并提交表单。

   ![](assets/optin_landingpage_2.png)

1. 提交表单后，将根据用 **[!UICONTROL General]** 户的选择更新配置文件选项卡。

   ![](assets/optin_landingpage_3.png)

### 设置登录页面以退出所有交付 {#setting-up-a-landing-page-to-opt-out-from-all-deliveries}

要允许用户从所有分发中选择退出，您必须创建并发布登 **[!UICONTROL BlackList]** 录页面。 有关创建登陆页面的详细信息，请参 [阅此页](../../channels/using/getting-started-with-landing-pages.md)。

用户单击登陆页面链接后，将自 **[!UICONTROL No longer contact (by any channel)]** 动选择配置文件中的选项。

![](assets/blacklisting_allchannels.png)

