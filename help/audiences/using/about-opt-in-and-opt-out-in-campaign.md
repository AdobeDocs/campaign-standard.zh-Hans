---
title: 关于 Campaign 中的选择启用和选择禁用
description: 选择退出会导致用户档案不再被任何投放或特定渠道的投放定向。
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
feature: Audiences
role: User
level: Beginner
exl-id: ccb35aeb-2b32-4444-969b-50021111a0d6
source-git-commit: 8be43668d1a4610c3388ad27e493a689925dc88c
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 8%

---

# 关于 Campaign 中的选择启用和选择禁用{#about-opt-in-and-opt-out-in-campaign}

选择退出会导致用户档案不再被任何投放或特定渠道的投放定向。

要为用户档案提供选择加入或选择退出的功能，您必须创建一个专用的登陆页面。 有关此内容的更多信息，请参阅[设置选择加入和选择退出登陆页面](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages)。

用户档案也可以由操作员手动选择加入或退出。 有关此内容的详细信息，请参阅[管理用户档案中的选择加入和选择退出](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile)。

在投放分析期间自动排除选择退出用户档案，以加快投放（错误率对投放速度有显着影响）。

>[!NOTE]
>
>选择退出适用于&#x200B;**用户档案**，而不是隔离到&#x200B;**电子邮件地址**&#x200B;或&#x200B;**电话号码**。 因此，选择禁用用户档案将从投放中排除与其关联的所有地址。 但是，如果用户在数据库中拥有两个用户档案，则投放仍会以该用户为目标，因为仅会选择禁用其其中一个用户档案。 要确保将其所有地址都排除在外，请将其添加到隔离的地址。 有关详细信息，请参见[此页面](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform)。

有关服务订阅的详细信息，请参阅[此页面](../../audiences/using/about-subscriptions.md)。
