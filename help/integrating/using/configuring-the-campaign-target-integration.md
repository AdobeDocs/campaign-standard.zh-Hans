---
title: 配置 Campaign-Target 集成
description: 了解如何配置Adobe Target集成，以开始在Adobe Campaign中使用动态内容。
page-status-flag: 从未激活
uuid: 0df5701c-dc26-4c30-9af9-ebf92815d90c
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: 集成
content-type: 参考
topic-tags: 使用系列活动和目标
discoiquuid: f7fb2084-dd6f-4aa2-940f-e4871314635
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 配置 Campaign-Target 集成{#configuring-the-campaign-target-integration}

Adobe Campaign与Adobe Target之间的集成允许您在交付中插入动态内容。

Adobe Campaign中首先需要配置才能使用与Adobe target的集成功能，且必须由职能管理员管理。

此过程需要以下元素：

* Adobe Experience cloud租户
* Adobe target租户
* 指定用于与Adobe Campaign建立连接的Adobe Target rawbox

1. 从高级菜单中，通过左上角的Adobe Campaign徽标，选择 **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Options]**。
1. 要为Adobe Target配置服务器和租户选项，请相应地填写以下字段：

   * **[!UICONTROL TNT_TenantName]**:Adobe target租户的名称。 此值与Adobe Target的名称相对应 **[!UICONTROL Client]**。
   * **[!UICONTROL TNT_EdgeServer]**:用于集成的Adobe Target服务器。 默认情况下，此选项已提供。 此值与Adobe Target对应 **[!UICONTROL Server Domain]**，后跟 **/m2** 值。 例如： **tt.omtrdc.net/m2**。
   ![](assets/tar_options.png)

您的用户现在可以使用Adobe Target在分发中添加动态图像。
