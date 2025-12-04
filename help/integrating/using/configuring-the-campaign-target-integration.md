---
title: 配置 Campaign-Target 集成
description: 了解如何配置Adobe Target集成，以便开始在Adobe Campaign中使用动态内容。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: d382bfdd-418d-46c1-98dd-df8626f85cac
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 4%

---

# 配置 Campaign-Target 集成{#configuring-the-campaign-target-integration}

Adobe Campaign与Adobe Target之间的集成允许您在投放中插入动态内容。

要在Adobe Campaign中使用与Adobe Target的集成功能，首先需要在中进行配置，并且必须由功能管理员进行管理。

此过程需要以下元素：

* Adobe Experience Cloud租户
* Adobe Target租户
* 为与Adobe Campaign建立连接而指定的Adobe Target rawbox

1. 从高级菜单中，通过左上角的Adobe Campaign徽标，选择&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**。
1. 要为Adobe Target配置服务器和租户选项，请相应地填写以下字段：

   * **[!UICONTROL TNT_TenantName]**： Adobe Target租户的名称。 此值对应于Adobe Target **[!UICONTROL Client]**&#x200B;的名称。
   * **[!UICONTROL TNT_EdgeServer]**：用于集成的Adobe Target服务器。 默认情况下已提供此选项。 此值对应于Adobe Target **[!UICONTROL Server Domain]**，后跟&#x200B;**/m2**&#x200B;值。 例如： **tt.omtrdc.net/m2**。

   ![](assets/tar_options.png)

您的用户现在可以使用Adobe Target在投放中添加动态图像。
