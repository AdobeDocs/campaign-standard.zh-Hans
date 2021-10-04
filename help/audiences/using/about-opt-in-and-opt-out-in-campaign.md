---
title: 关于 Campaign 中的选择启用和选择禁用
description: 选择退出会导致用户档案不再为任何投放或特定渠道的投放所定向。
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
feature: Audiences
role: User
level: Beginner
exl-id: ccb35aeb-2b32-4444-969b-50021111a0d6
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 8%

---

# 关于 Campaign 中的选择启用和选择禁用{#about-opt-in-and-opt-out-in-campaign}

选择退出会导致用户档案不再为任何投放或特定渠道的投放所定向。

为了让用户档案能够选择启用或选择禁用，您必须创建专用登陆页面。 有关更多信息，请参阅[设置选择启用和选择禁用登陆页面](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages)。

操作员也可以手动选择启用或禁用用户档案。 有关更多信息，请参阅[管理配置文件的选择启用和选择禁用。](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile)

在投放分析期间，会自动排除选择退出用户档案，以加快投放速度（错误率对投放速度有显着影响）。

>[!NOTE]
>
>选择退出适用于&#x200B;**Profiles**，而不是与链接到&#x200B;**电子邮件地址**&#x200B;或&#x200B;**电话号码**&#x200B;的隔离。 因此，选择退出用户档案将从投放中排除链接到该用户档案的所有地址。 但是，如果用户在数据库中有两个用户档案，则投放仍会定位此用户，因为只选择其其中一个用户档案。 要确保将他的所有地址都排除在外，请将其添加到隔离的地址中。 有关详细信息，请参见[此页面](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform)。

有关服务订阅的更多信息，请参阅[本页](../../audiences/using/about-subscriptions.md)。
