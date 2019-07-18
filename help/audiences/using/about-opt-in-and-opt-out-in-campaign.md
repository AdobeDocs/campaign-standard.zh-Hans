---
title: 关于Campaign中的选择加入和退出
seo-title: 关于Campaign中的选择加入和退出
description: 关于Campaign中的选择加入和退出
seo-description: 选择退出(或黑名单)不再为任何交付或特定渠道提供的分发定位。
page-status-flag: 从未激活
uuid: 501d9485-976b-4de7-b242-6886f2814 c6 c
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 受众
content-type: reference
topic-tags: 了解退出和选择退出流程
discoiquuid: 2f26ec22-0809-4541-b2 a1-e84 ff868 ba6 e
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# About opt-in and opt-out in Campaign{#about-opt-in-and-opt-out-in-campaign}

选择退出(或黑名单)不再为任何交付或特定渠道提供的分发定位。

要为配置文件提供选择退出或退出的功能，您必须创建专用登录页面。For more on this, refer to [Setting up opt-in and opt-out landing pages](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages).

配置文件也可以由操作符手动选择或退出。For more on this, refer to [Managing opt-in and opt-out from a profile](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile).

选择退出配置文件会在交付分析过程中自动排除，从而加快交付(错误率对交付速度有显著影响)。

>[!NOTE]
>
>Opt-out applies to **Profiles**, as opposed to quarantine which is linked to an **email address** or **phone number**. 因此，选择退出配置文件将排除所有链接到该配置文件的地址。如果用户在数据库中有两个档案，则仍将通过分发定位他，因为其只有一个档案选择退出。为确保排除其所有疏忽，请将其添加到四分性地址。For more on this, refer to [this page](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform).

For more on services subscriptions, refer to [this page](../../audiences/using/about-subscriptions.md).
