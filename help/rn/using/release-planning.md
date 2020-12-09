---
solution: Campaign Standard
product: campaign
title: Campaign Standard 发行计划
description: 本页列出了即将发行的 Adobe Campaign Standard 版本。
audience: rn
content-type: reference
topic-tags: campaign-standard-release-planning
translation-type: ht
source-git-commit: ad7322905c69f9575e11efc9d8f68cf909dc425f
workflow-type: ht
source-wordcount: '452'
ht-degree: 100%

---


# 发行计划{#release-planning}

Adobe 通过添加新功能、增强功能和修复错误，不断改进其解决方案。

所有 Adobe Campaign Standard 实例都会随每次版本更新一起升级。升级不需要任何操作。

升级分两个阶段进行。首先，升级 Stage 实例，使我们的客户能够测试新功能并根据需要调整其配置随后将升级 Production 实例。

所有发行日期随时可能更改：我们建议您定期访问此页面以查看更新。

**最新！**&#x200B;请订阅 [Campaign Standard 发行通知](http://amc-mkt-prod1-t.adobe-campaign.com/lp/LP25?service=%40rZ5cqp2DgNzrgz0alKPInakNbPSTeJYozZYnS7Wbs802u4GlISkHZX4omtK00nAU6xzZ6luEWQzr7kQ9pkCwJYumWkU)，以通过电子邮箱接收关于最新版本的详情。

## 21.1 版 - 2 月发布 {#release-21-1-release}

在下方指定的时间段内，将不定时进行环境更新。有关此版本的详细信息，请参阅[发行说明](../../rn/using/release-notes.md)。如果您有其他问题，请联系 [Adobe 客户服务](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html)。

<table>
 <thead>
  <tr>
   <th> 环境<br /> </th>
   <th> 日期<br /> </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>Stage<br /> </td>
   <td>2021 年 1 月 25 日至 27 日<br /> </td>
  </tr>
  <tr>
   <td> Production<br /> </td>
   <td>2021 年 2 月 1 日至 8 日<br /> </td>
  </tr>
 </tbody>
</table>

## 问题与回答{#questions-and-answers}

**问：受影响的范围包括？**

答：[发行说明](../../rn/using/release-notes.md)中列出了更改，包括相关文档的链接。Adobe 还建议查阅[已弃用和已删除的功能页面](../../rn/using/deprecated-features.md)。新版本会在 Stage 环境升级的日期提供这些页面。

**问：采用什么验证流程？**

答：升级 Stage 阶段的实例时，Adobe 建议验证您的流程和使用案例是否能使用此新版本正常工作，并向 [Adobe 客户服务](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html)报告任何问题。

**问：在升级过程中是否可以访问实例？**

答：不行。在实例升级过程中，可能有几分钟无法访问数据库。所有流程都会自动重新启动。

**问：是否会继续发送消息？**

答：不会。有几分钟不会发送消息。一旦升级完成，流程就会自动重新启动。

**问：工作流是否会继续运行并发送投放？**

答：不会。在版本升级的过程中，工作流服务器和 MTA 都会停止。这意味着在几分钟内，不会运行工作流，也不会发送投放。无需执行任何操作：一旦实例升级完成，工作流将立即重新启动。

**问：在升级过程中，消息中的跟踪链接是否仍然有效？**

答：是的，它们仍然有效。升级期间无法发送新电子邮件，但已发送电子邮件中包含的跟踪链接可正常使用。

**问：如何知晓升级已完成？**

答：登录到 Campaign 时，将显示最新版本发行说明弹出窗口。

如有其他问题，请联系 [ Adobe 客户服务](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html)。
