---
solution: Campaign Standard
product: campaign
title: 关于 Campaign 中的选择启用和选择禁用
description: 选择退出会导致用户档案不再为任何投放或特定渠道的投放所针对。
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 9%

---


# 关于 Campaign 中的选择启用和选择禁用{#about-opt-in-and-opt-out-in-campaign}

选择退出会导致用户档案不再为任何投放或特定渠道的投放所针对。

要让用户档案能够选择加入或选择退出者，您必须创建专用登陆页。 有关此内容的详细信 [息，请参阅设置选择加入和选择退出登陆页](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages)。

用户档案也可以由操作员手动选择加入或退出。 有关此内容的详细信 [息，请参阅管理用户档案的加入和退出](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile)。

选择退出用户档案在投放分析期间自动被排除，以加快投放(错误率对投放速度有显着影响)。

>[!NOTE]
>
>选择退出适用于 **用户档案**，而不是链接到电子邮件地 **址或电** 话号码的隔离 ****。 因此，选择退出用户档案将从投放中排除与其链接的所有地址。 如果用户在用户档案库中有两个投放，他仍然会被锁定，因为只有一个用户档案选择退出。 要确保其所有地址都被排除，请将其添加到隔离地址。 有关详细信息，请参见[此页面](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform)。

For more on services subscriptions, refer to [this page](../../audiences/using/about-subscriptions.md).
