---
solution: Campaign Standard
product: campaign
title: 配置 Campaign-Target 集成
description: 了解如何将Adobe Target集成配置为在Adobe Campaign中使用动态内容进行开始。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 4%

---


# 配置 Campaign-Target 集成{#configuring-the-campaign-target-integration}

Adobe Campaign与Adobe Target之间的集成允许您在投放中插入动态内容。

在Adobe Campaign中，首先需要配置才能使用与Adobe Target的集成功能，且必须由功能管理员管理。

此过程需要以下元素：

* Adobe Experience Cloud租户
* Adobe Target租户
* 为建立与Adobe Campaign的连接而指定的Adobe Target罗博克斯

1. 从高级菜单中，通过左上角的Adobe Campaign标志，选择&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**。
1. 要为Adobe Target配置服务器和租户选项，请相应地填写以下字段：

   * **[!UICONTROL TNT_TenantName]**:adobe target租户的名字。此值与Adobe Target **[!UICONTROL Client]**&#x200B;的名称相对应。
   * **[!UICONTROL TNT_EdgeServer]**:Adobe Target服务器用于集成。默认情况下，此选项已提供。 此值与Adobe Target **[!UICONTROL Server Domain]**&#x200B;对应，后跟&#x200B;**/m2**&#x200B;值。 例如：**tt.omtrdc.net/m2**。

   ![](assets/tar_options.png)

您的用户现在可以在与Adobe Target的投放中添加动态图像。
