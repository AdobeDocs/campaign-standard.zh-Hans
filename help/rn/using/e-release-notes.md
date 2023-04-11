---
title: 早期发行说明
description: 早期发行说明
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 485927b217fb68064897dd877c2f4a6dd208d443
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 21%

---


# 早期发行说明 {#e-new-release}

本页介绍了下一个 Campaign Standard 版本中包含的改进和修复。
>[!CAUTION]
>
> 在暂存环境升级日期之前，此内容可能会有所变动，恕不另行通知。在[发行计划页面](../../rn/using/release-planning.md)中了解详情。

## 23.1 版 - 2023 年春/夏季版 {#apr-23}

### 改进 {#e-rn-improvements}

* 推送消息服务已现代化，以改进支持。 (CAMP-47959)
* 短信消息传送服务已得到改进，以提供更好的稳定性。 (CAMP-52217)
* Adobe进行了许多辅助功能修复，以提高应用程序的整体易用性。 以下是一些辅助功能改进示例：
   * 界面的键盘辅助功能已在许多屏幕中得到优化。
   * 已为触摸屏用户增强了应用程序。
   * 整个界面中多个项目的颜色已更改，以提高可见性。

### 其他变更 {#e-rn-changes}

* 开箱即用 **报告扩充创建工作流** 已添加。 在将目标映射从一个实例导入另一个实例后，只需运行工作流以导入相应的报表扩充条目。 (CAMP-52452)

### 已修复的问题{#e-rn-patches}

* 修复了在显示 **热点单击** 报表。 (CAMP-51582)
* 修复了可能会阻止您使用与 **位置** 服务。 (CAMP-51923)
* 修复了可能阻止工作流计划程序正常工作的问题。 (CAMP-52003)
* 修复了在查看包含大量数据的自定义动态报表的PDF版本时，划分详细信息无法显示的问题。 (CAMP-52178)
* 修复了访问报告时可能显示错误的问题。 (CAMP-52500)
* 修复了错误应用 **限制此帐户的MTA实例** SMS连接器参数应用于所有渠道，而不是仅应用于SMS。 (CAMP-52640)
