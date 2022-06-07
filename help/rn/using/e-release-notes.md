---
title: 早期发行说明
description: 早期发行说明
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 30%

---

# 早期发行说明 {#new-release}

本页介绍了下一个 Campaign Standard 版本中包含的新增功能、改进和修复。

>[!CAUTION]
>
> 在暂存环境升级日期之前，此内容可能会有所变动，恕不另行通知。在[发行计划页面](../../rn/using/release-planning.md)中了解详情。

## 22.2 版 - 2022 年 6 月 {#rn-2022}

**改进**

* **Adobe 通知服务** - Campaign 附带“Adobe 通知服务”，此服务允许 Experience Cloud 解决方案提醒 Experience Cloud 的用户注意对他们而言非常重要的活动。从版本 22.2 开始，用户体验得到了改进：通知按优先顺序排列，产品生成的通知与 Adobe 状态公告分开。此外，当通知提及特定工作流时，您现在可以直接从电子邮件或产品内通知访问相应的工作流。有关 Adobe Campaign 通知的更多信息，请参阅 [Adobe Campaign 通知](../../administration/using/sending-internal-notifications.md)。

* **工作流启动中的优化** -Adobe添加了一项新功能，可以调整大约在同一时间开始的工作流数量。 这将有助于防止可能导致服务中断或停机的CPU尖峰。 Adobe将在22.2版本之后启用它。 对于客户，没有关于该事项的其他操作项目。

* **辅助功能** -Adobe进行了许多无障碍修复，以提高应用程序的整体易用性。 这些功能目前仅为一组早期采用者启用，并将在ACS 22.3版本中向所有客户推出。 辅助功能改进的示例包括：

   * 确保每个屏幕上有可聚焦元素的可见焦点指示器
   * 创建页面地标以更便于导航
   * 添加许多控件的名称、角色、值和状态
   * 更正主屏幕上动态焦点顺序遇到的问题

**安全升级**

* 已将Apache Tomcat从版本7升级到版本8.5。


**修补程序**

* 修复了由于密钥重复错误导致计费技术工作流上的问题。 (CAMP-51029)
* 在跟踪报表中添加了缺失的Microsoft Edge浏览器类别。 之前，在Microsoft Chrome打开时，会对这些用户进行分类。 (CAMP-51165)
* 修复了GDPR请求无法从子表中删除数据的问题。 (CAMP-48276)
* 修复了Email Designer中导致无法在事务型消息模板中保存片段的可见性条件的问题。 (CAMP-50338)
* 修复了营销活动报表中导致日期范围未被考虑的问题。 (CAMP-50991)
* 修复了导致计划电子邮件失败的错误：投放分析无法启动，因为投放仍处于“重试挂起”状态。 (CAMP-50302)
* 修复了在预览具有用户档案替换的电子邮件时，Email Designer中出现的问题。 (CAMP-49312)
* 修复了自定义枚举中值为空的问题：在创建自定义资源时，如果某个字段是文本枚举并且只包含一个值，则现在默认情况下会设置此值，以便您可以将此字段上的查询创建为简单请求。 (CAMP-50606)
