---
solution: Campaign Standard
product: campaign
title: 管理 Campaign 中的选择启用和选择禁用
description: 了解如何在Adobe Campaign中管理选择加入和选择退出。
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 8%

---


# 管理 Campaign 中的选择启用和选择禁用{#managing-opt-in-and-opt-out-in-campaign}

## 管理用户档案的加入和退出 {#managing-opt-in-and-opt-out-from-a-profile}

操作员可以直接从“用户档案”选项卡选择加入或退出 **[!UICONTROL General]** 用户。

在部 **[!UICONTROL No longer contact (on denylist)]** 分中，选定的复选框与用户选择的渠道对选择退出应。 根据用户的需要选择渠道。

![](assets/optin_landingpage_3.png)

## 设置选择加入和选择退出登陆页 {#setting-up-opt-in-and-opt-out-landing-pages}

要使用户能够选择加入或选择退出者，您必须创建和发布 **[!UICONTROL Profile acquisition]** 登陆页。 然后，他们可以根据自己的需要选择渠道。 为此，请执行以下步骤：

您还可以设置一个 **[!UICONTROL Denylist]** 登陆页，使用户能够从选择退出所有投放访问。 有关此内容的详细信息，请 [参阅从所有登陆页选择退出中设置投放](#setting-up-a-landing-page-to-opt-out-from-all-deliveries)。

>[!NOTE]
>
>登陆页还可用于启用服务订阅。 有关详细信息，请参见[此页面](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service)。

1. 创建 **[!UICONTROL Profile acquisition]** 登陆页(请 [参阅本部](../../channels/using/getting-started-with-landing-pages.md))。
1. 在登陆页内容中为每个所需的渠道添加一个复选框，然后将其链接到活动库中的相应字段。

   ![](assets/optin_landingpage_1.png)

1. 保存登陆页并发布。
1. 在登陆页中，复选框已根据用户档案选项卡进行选 **[!UICONTROL General]** 择。 用户可以根据自己的需要选择或取消选择渠道并提交表单。

   ![](assets/optin_landingpage_2.png)

1. 提交表单后，用户档案 **[!UICONTROL General]** 选项卡会根据用户的选择进行更新。

   ![](assets/optin_landingpage_3.png)

### 将登陆页设置选择退出为所有投放 {#setting-up-a-landing-page-to-opt-out-from-all-deliveries}

要使用户能够从所选择退出有投放创建和发布 **[!UICONTROL Denylist]** 登陆页。 有关登陆页创建的详细信息，请参 [阅本页](../../channels/using/getting-started-with-landing-pages.md)。

用户单击登陆页链接后，用户档案 **[!UICONTROL No longer contact (by any channel)]** 中的选项将自动选中。

![](assets/blocklisting_allchannels.png)

