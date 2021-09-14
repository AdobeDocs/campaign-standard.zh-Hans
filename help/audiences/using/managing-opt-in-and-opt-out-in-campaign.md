---
title: 管理 Campaign 中的选择启用和选择禁用
description: 了解如何在Adobe Campaign中管理选择启用和选择禁用。
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
feature: Audiences
role: User
level: Intermediate
exl-id: 4aeb90c5-f5b5-4cfe-93fb-2fd01fb8d70e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 8%

---

# 管理 Campaign 中的选择启用和选择禁用{#managing-opt-in-and-opt-out-in-campaign}

## 管理用户档案的选择启用和选择禁用 {#managing-opt-in-and-opt-out-from-a-profile}

操作员可以直接从用户档案&#x200B;**[!UICONTROL General]**&#x200B;选项卡中选择加入或退出用户。

在&#x200B;**[!UICONTROL No longer contact (on denylist)]**&#x200B;部分中，选定的复选框对应于用户选择退出的渠道。 根据用户的需求选择渠道。

![](assets/optin_landingpage_3.png)

## 设置选择启用和选择禁用登陆页面 {#setting-up-opt-in-and-opt-out-landing-pages}

要允许用户选择启用或选择禁用，您必须创建并发布&#x200B;**[!UICONTROL Profile acquisition]**&#x200B;登陆页面。 然后，他们将能够根据自己的需求选择渠道。 为此，请执行以下步骤：

您还可以设置一个&#x200B;**[!UICONTROL Denylist]**&#x200B;登陆页面，以允许用户选择退出所有投放。 有关更多信息，请参阅[设置登陆页面以选择退出所有投放](#setting-up-a-landing-page-to-opt-out-from-all-deliveries)。

>[!NOTE]
>
>登陆页面还可用于启用服务订阅。 有关详细信息，请参见[此页面](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service)。

1. 创建&#x200B;**[!UICONTROL Profile acquisition]**&#x200B;登陆页面（请参阅[此部分](../../channels/using/getting-started-with-landing-pages.md)）。
1. 在登陆页面内容中为每个所需渠道添加一个复选框，然后将其链接到Campaign数据库中的相应字段。

   ![](assets/optin_landingpage_1.png)

1. 保存登陆页面并发布该页面。
1. 在登陆页面中，已根据用户档案&#x200B;**[!UICONTROL General]**&#x200B;选项卡选中相应复选框。 用户可以根据需要选择或取消选择渠道并提交表单。

   ![](assets/optin_landingpage_2.png)

1. 提交表单后，将根据用户的选择更新用户档案&#x200B;**[!UICONTROL General]**&#x200B;选项卡。

   ![](assets/optin_landingpage_3.png)

### 设置登陆页面以选择退出所有投放 {#setting-up-a-landing-page-to-opt-out-from-all-deliveries}

要允许用户选择退出所有投放，您必须创建并发布&#x200B;**[!UICONTROL Denylist]**&#x200B;登陆页面。 有关登陆页面创建的更多信息，请参阅[此页面](../../channels/using/getting-started-with-landing-pages.md)。

用户单击登陆页面链接后，配置文件中的&#x200B;**[!UICONTROL No longer contact (by any channel)]**&#x200B;选项将自动选中。

![](assets/blocklisting_allchannels.png)
