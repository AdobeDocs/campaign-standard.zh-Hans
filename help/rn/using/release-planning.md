---
title: Campaign Standard发布计划
description: 本页列表即将发布的Adobe Campaign标准版。
page-status-flag: never-activated
uuid: null
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-release-planning
discoiquuid: null
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: fb865ae08a4b0db42b71e58895976a973a2ed6b7
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 1%

---


# 发行计划 {#release-planning}

Adobe通过添加新功能、增强和修复不断改进其解决方案。

所有Adobe Campaign标准实例都随每个新版本一起升级。 升级不需要任何操作。

升级分两个阶段进行。 首先，升级Stage实例，使我们的客户能够测试新功能并根据需要调整其配置。 随后将升级生产实例。

所有发布日期均可能更改： 我们建议您定期访问此页面以检查更新。

**最新！** 订阅Campaign Standard [发布通知](http://amc-mkt-prod1-t.adobe-campaign.com/lp/LP25?service=%40rZ5cqp2DgNzrgz0alKPInakNbPSTeJYozZYnS7Wbs802u4GlISkHZX4omtK00nAU6xzZ6luEWQzr7kQ9pkCwJYumWkU) ，直接在您的收件箱中获取有关即将发布版本的详细信息。

## 版本20.3.1 - 5月版 {#release-20-3-may-release}

环境更新在批次中发生，时间为以下指定时间帧。 有关此版本的详细信息，请参阅发 [行说明](../../rn/using/release-notes.md)。 如果您有其他问题，请联系 [Adobe客户关怀](https://support.neolane.net/webApp/extranetLogin)。

<table>
 <thead>
  <tr>
   <th> 环境<br /> </th>
   <th> 日期<br /> </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>舞台<br /> </td>
   <td>2020年5月26日至27日<br /> </td>
  </tr>
  <tr>
   <td> 制作<br /> </td>
   <td>2020年5月28日至6月1日<br /> </td>
  </tr>
 </tbody>
</table>



## 问题与答案 {#questions-and-answers}

**问： 影响是什么？**

答： 发行说明中列出了 [更改](../../rn/using/release-notes.md)，包括相关文档的链接。 Adobe还建议查阅已弃 [用和已删除功能页](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)。 这些页面在阶段环境升级日期可用于新版本。

**问： 验证过程是什么？**

答： 升级登台实例时，Adobe建议验证您的进程和使用案例是否能使用此新版本正常工作，并向Adobe Client Care报 [告任何问题](https://support.neolane.net/webApp/extranetLogin)。

**问： 在升级过程中是否可以访问该实例？**

答： 不。 在实例升级过程中，数据库可能在几分钟内无法访问。 所有进程都自动重新启动。

**问： 消息是否会继续发送？**

答： 不。 几分钟内不会发送消息。 升级一完成，进程就会自动重新启动。

**问： 工作流会继续运行并发送投放吗？**

答： 不。 在构建升级过程中，工作流服务器和MTA都停止。 这意味着工作流在几分钟内不运行，投放也不发送。 无需执行任何操作： 工作流将在实例升级后立即再次开始。

**问： 在升级过程中，跟踪邮件中的链接是否仍然有效？**

答： 是的，它们会起作用。 升级期间无法发送新电子邮件，但跟踪已发送电子邮件中包含的链接将可正常使用。

**问： 如何知道升级已完成？**

答： 登录到活动时，将显示包含最新版本的发布通知弹出窗口。

如有其他问题，请与Adobe [客户关怀部门联系](https://support.neolane.net/webApp/extranetLogin)。
