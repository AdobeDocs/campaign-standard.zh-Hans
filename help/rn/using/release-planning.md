---
title: Campaign standard发布计划
description: 本页列出了Adobe Campaign standard即将发布的版本。
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
source-git-commit: 184a878f7be573a6b45a3a2853c07029432392f0

---


# 发布计划 {#release-planning}

Adobe通过添加新功能、增强和修复不断改进其解决方案。

所有Adobe Campaign standard实例都随每个新版本一起升级。 升级不需要任何操作。

升级分两个阶段部署。 首先，升级了Stage实例，使我们的客户能够测试新功能并根据需要调整其配置。 随后将升级生产实例。

所有发布日期均可更改：我们建议您定期访问此页面以检查更新。

订阅后，请 [直接在您的收件箱中接收发布通知](https://www.adobe.com/subscription/priority-product-update.html) ，以获取有关最新Adobe Experience cloud版本的详细信息。

## 版本20.1.4 - 2月版本更新 {#release-20-1-4---february-release-update}

环境更新在以下指定时间段内以波浪形式发生。 有关此版本的详细信息，请参阅发 [行说明](../../rn/using/release-notes.md)。 如果您有其他问题，请联系 [Adobe客户服务](https://support.neolane.net/webApp/extranetLogin)。

<table> 
 <thead> 
  <tr> 
   <th> 环境<br /> </th> 
   <th> 日期<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Stage<br /> </td> 
   <td> 2020年2月17日至18日<br /> </td> 
  </tr> 
  <tr> 
   <td> 制作<br /> </td> 
   <td> 2020年2月20日至3月5日<br /> </td> 
  </tr> 
 </tbody> 
</table>



## 问题与答案 {#questions-and-answers}

**问：影响何在？**

答：发行说明中列出了 [更改](../../rn/using/release-notes.md)，包括相关文档的链接。 Adobe还建议查阅已弃用 [和已删除功能页面](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)。 这些页面在升级阶段环境的日期可用于新版本。

**问：验证过程是什么？**

答：升级登台实例时，Adobe建议验证您的流程和使用案例是否可以使用此新版本正常工作，并向 [Adobe Client Care报告任何问题](https://support.neolane.net/webApp/extranetLogin)。

**问：在升级过程中是否可以访问该实例？**

答：不。 在实例升级过程中，数分钟内可能无法访问数据库。 所有进程都会自动重新启动。

**问：消息是否将继续发送？**

答：不。 几分钟内不会发送消息。 升级一完成，进程就会自动重新启动。

**问：工作流是否将继续运行并发送提交？**

答：不。 在构建升级过程中，工作流服务器和MTA都停止。 这意味着工作流在几分钟内不会运行，也不会发送。 无需执行任何操作：在实例升级后，工作流将立即重新启动。

**问：在升级过程中，跟踪消息中的链接是否仍然有效？**

答：是的，它们会起作用的。 升级期间无法发送新电子邮件，但跟踪已发送电子邮件中包含的链接将可正常使用。

**问：如何知道升级已完成？**

答：登录营销活动时，将显示一个包含最新版本的发布通知弹出窗口。

如有任何其他问题，请与 [Adobe客户关怀联系](https://support.neolane.net/webApp/extranetLogin)。