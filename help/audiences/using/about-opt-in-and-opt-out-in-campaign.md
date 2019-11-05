---
title: 关于 Campaign 中的选择启用和选择禁用
description: 选择退出（或黑名单）导致任何分发或特定渠道的分发不再针对配置文件。
page-status-flag: 从未激活
uuid: 501d9485-976b-4de7-b242-6886f2814c6c
contentOwner: 绍维亚
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: 参考
topic-tags: 了解——选择加入——选择退出流程
discoiquuid: 2f26ec22-0809-4541-b2a1-e84ff868ba6e
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 关于 Campaign 中的选择启用和选择禁用{#about-opt-in-and-opt-out-in-campaign}

选择退出（或黑名单）导致任何分发或特定渠道的分发不再针对配置文件。

要使配置文件能够选择加入或选择退出，您必须创建一个专用的登录页面。 有关详细信息，请参 [阅设置选择加入和选择退出登录页面](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages)。

操作员还可以手动选择加入或退出配置文件。 有关详细信息，请参 [阅从配置文件管理选择加入和选择退出](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile)。

在交付分析期间，选择退出配置文件会自动被排除以加快交付（错误率对交付速度有显着影响）。

>[!NOTE]
>
>选择退出适用于配 **置文件**，而不是链接到电子邮件地址或电话号 **码的隔** 离选项 ****。 因此，选择退出配置文件将从分发中排除所有与其链接的地址。 如果用户在数据库中有两个配置文件，他仍将被提交作为目标，因为只有一个配置文件是选择退出的。 为确保他的所有地址都被排除，请将其添加到隔离地址。 有关详细信息，请参见[此页面](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform)。

For more on services subscriptions, refer to [this page](../../audiences/using/about-subscriptions.md).
