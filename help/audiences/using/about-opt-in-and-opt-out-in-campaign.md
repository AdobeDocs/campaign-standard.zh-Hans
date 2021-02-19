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

要让用户档案能够选择加入或选择退出者，您必须创建专用登陆页。 有关详细信息，请参阅[设置选择加入和选择退出登陆页](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages)。

用户档案也可以由运算符手动选择加入或退出。 有关详细信息，请参阅[管理用户档案](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile)中的选择加入和选择退出。

选择退出用户档案在投放分析期间自动被排除，以加快投放(错误率对投放速度有显着影响)。

>[!NOTE]
>
>选择退出适用于&#x200B;**用户档案**，而不是链接至&#x200B;**电子邮件地址**&#x200B;或&#x200B;**电话号码**&#x200B;的隔离。 因此，选择退出用户档案将从投放中排除所有与其链接的地址。 如果用户在数据库中有两个用户档案，他仍然会被投放瞄准，因为他的用户档案中只有一个是选择退出的。 要确保其所有地址都被排除，请将其添加到隔离地址。 有关详细信息，请参见[此页面](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform)。

有关服务订阅的详细信息，请参阅[此页](../../audiences/using/about-subscriptions.md)。
