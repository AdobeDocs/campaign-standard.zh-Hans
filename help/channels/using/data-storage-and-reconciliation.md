---
title: 数据存储和和解
seo-title: 数据存储和和解
description: 数据存储和和解
seo-description: Adobe Campaign允许您定义用户提交登陆页面中输入的数据后如何管理。
page-status-flag: 从未激活
uuid: 5b222ea2-6628-457f-a618-bfc0 e5 eb93 dd
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 频道
content-type: reference
topic-tags: 登录页面
discoiquuid: 899c7152-f415-4df9-b4 b4-5ff3470 a4 e32
context-tags: LandingPage，主要
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: d50d486ed77cb7989df47133bb49fde3227ae3a5

---


# Data storage and reconciliation{#data-storage-and-reconciliation}

数据分类参数允许您定义在用户提交登陆页面中输入的数据后，如何管理该数据。

要执行此操作，请执行以下操作：

1. Edit the landing page properties accessed via the ![](assets/edit_darkgrey-24px.png) icon in the landing page dashboard, and display the **[!UICONTROL Job]** parameters.

   ![](assets/lp_parameters_4.png)

1. Select the **[!UICONTROL Reconciliation key]**: these database fields (for example: email, first name, last name) are used to determine whether the visitor has a profile that is already known in the Adobe Campaign database. 这允许您根据定义的更新策略参数更新或创建配置文件。
1. Define the **[!UICONTROL Form parameter mapping]**: this section allows you to map the landing page field parameters and those used in the reconciliation key.
1. Select the **[!UICONTROL Update strategy]**: if the reconciliation key recovers an existing database profile, you can choose for this profile to be updated with the data entered in the form or instead prevent this update.

