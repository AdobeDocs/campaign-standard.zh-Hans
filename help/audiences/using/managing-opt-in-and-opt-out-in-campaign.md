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
source-git-commit: 8be43668d1a4610c3388ad27e493a689925dc88c
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 8%

---

# 管理 Campaign 中的选择启用和选择禁用{#managing-opt-in-and-opt-out-in-campaign}

## 管理用户档案的选择启用和选择禁用 {#managing-opt-in-and-opt-out-from-a-profile}

操作员可以直接从用户档案中选择加入或退出用户 **[!UICONTROL General]** 选项卡。

在 **[!UICONTROL No longer contact (on denylist)]** 部分，则选定的复选框对应于用户选择退出的渠道。 根据用户的需求选择渠道。

![](assets/optin_landingpage_3.png)

## 设置选择启用和选择禁用登陆页面 {#setting-up-opt-in-and-opt-out-landing-pages}

要允许用户选择启用或选择禁用，您必须创建并发布 **[!UICONTROL Profile acquisition]** 登陆页面。 然后，他们将能够根据自己的需求选择渠道。 为此，请执行以下步骤：

您还可以设置 **[!UICONTROL Denylist]** 登陆页面，让用户能够选择退出所有投放。 有关更多信息，请参阅 [设置登陆页面以选择退出所有投放](#setting-up-a-landing-page-to-opt-out-from-all-deliveries).

>[!NOTE]
>
>登陆页面还可用于启用服务订阅。 有关详细信息，请参见[此页面](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service)。

1. 创建 **[!UICONTROL Profile acquisition]** 登陆页面(请参阅 [此部分](../../channels/using/getting-started-with-landing-pages.md))。
1. 在登陆页面内容中为每个所需渠道添加一个复选框，然后将其链接到Campaign数据库中的相应字段。

   ![](assets/optin_landingpage_1.png)

1. 保存登陆页面并发布该页面。
1. 在登陆页面中，已根据用户档案选中相应的复选框 **[!UICONTROL General]** 选项卡。 用户可以根据需要选择或取消选择渠道并提交表单。

   ![](assets/optin_landingpage_2.png)

1. 提交表单后，用户档案 **[!UICONTROL General]** 选项卡会根据用户的选择进行更新。

   ![](assets/optin_landingpage_3.png)

### 设置登陆页面以选择退出所有投放 {#setting-up-a-landing-page-to-opt-out-from-all-deliveries}

要允许用户选择退出所有投放，您必须创建并发布 **[!UICONTROL Denylist]** 登陆页面。 有关创建登陆页面的更多信息，请参阅 [本页](../../channels/using/getting-started-with-landing-pages.md).

用户单击登陆页面链接后， **[!UICONTROL No longer contact (by any channel)]** 选项。

![](assets/blocklisting_allchannels.png)
