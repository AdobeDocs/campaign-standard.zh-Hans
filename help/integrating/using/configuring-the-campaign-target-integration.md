---
title: 配置Campaign-Target集成
seo-title: 配置Campaign-Target集成
description: 配置Campaign-Target集成
seo-description: 了解如何配置Adobe Target集成以开始在Adobe Campaign中使用动态内容。
page-status-flag: 从未激活
uuid: 0df5701c-dc26-4c30-9af9-ef92815 d90 c
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 集成
content-type: reference
topic-tags: 使用营销活动和目标
discoiquuid: f7fb2084-dd6 f-4aa2-940f-e48713146635
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Configuring the Campaign-Target integration{#configuring-the-campaign-target-integration}

Adobe Campaign与Adobe Target之间的集成允许您在交付中插入动态内容。

在Adobe Campaign中，首先需要配置才能使用Adobe Target的集成功能，并且必须由职能管理员管理。

此过程需要以下元素：

* Adobe Experience Cloud租户
* Adobe Target租户
* 指定用于与Adobe Campaign建立连接的Adobe Target rawbox

1. From the advanced menu, via the Adobe Campaign logo in the top left corner, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Options]**.
1. 要为Adobe Target配置服务器和租户选项，请相应地填写以下字段：

   * **[!UICONTROL TNT_TenantName]**：Adobe Target租户的名称。This value corresponds to the name of the Adobe Target **[!UICONTROL Client]**.
   * **[!UICONTROL TNT_EdgeServer]**：用于集成的Adobe Target服务器。默认情况下已提供此选项。This value corresponds to the Adobe Target **[!UICONTROL Server Domain]**, followed by the **/m2** value. For example: **tt.omtrdc.net/m2**.
   ![](assets/tar_options.png)

用户现在可以使用Adobe Target在分发中添加动态图像。
