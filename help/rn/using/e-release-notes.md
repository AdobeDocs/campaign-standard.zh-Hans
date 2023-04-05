---
title: 早期发行说明
description: 早期发行说明
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 25e842d2b012a07b3f1ef1ff5490a6b4afa0e887
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 27%

---


# 早期发行说明 {#e-new-release}

本页介绍了下一个 Campaign Standard 版本中包含的改进和修复。
>[!CAUTION]
>
> 在暂存环境升级日期之前，此内容可能会有所变动，恕不另行通知。在[发行计划页面](../../rn/using/release-planning.md)中了解详情。

## 23.1 版 - 2023 年春/夏季版 {#apr-23}

### 改进 {#e-rn-improvements}

* 推送消息服务已现代化以优化维护。 (CAMP-47959)
* 短信消息传送服务已经现代化，以提供改进的稳定性。 (CAMP-52217)
* 开箱即用 **报告扩充创建工作流** 已添加。 在将目标映射从一个实例导入另一个实例后，只需运行工作流以导入相应的报表扩充条目。 (CAMP-52452)

### 修补程序{#e-rn-patches}

* 修复了在显示 **热点单击** 报表。 (CAMP-51582)
* 修复了可能会阻止您使用与 **位置** 服务。 (CAMP-51923)
* 修复了可能阻止工作流计划程序正常工作的问题。 (CAMP-52003)
* 修复了在查看包含大量数据的自定义动态报表的PDF版本时，划分详细信息无法显示的问题。 (CAMP-52178)
* 修复了访问报告时可能显示错误的问题。 (CAMP-52500)
* 修复了错误应用 **限制此帐户的MTA实例** SMS连接器参数应用于所有渠道，而不是仅应用于SMS。 (CAMP-52640)
