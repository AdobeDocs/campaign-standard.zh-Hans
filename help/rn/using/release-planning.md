---
title: Campaign Standard 发行计划
description: 本页列出了即将发行的 Adobe Campaign Standard 版本。
audience: rn
content-type: reference
topic-tags: campaign-standard-release-planning
feature: Overview
role: User
level: Beginner
exl-id: 1f48d4da-5622-4fab-af87-fcce0e40ade1
source-git-commit: c35f8caeab9b6605b042618705eecc347d13fd18
workflow-type: ht
source-wordcount: '419'
ht-degree: 100%

---

# 发行计划 {#release-planning}

Adobe 通过添加新功能、增强功能和修复错误，不断改进其解决方案。

所有 Adobe Campaign Standard 实例都会随每次版本更新一起升级。升级不需要任何操作。

升级分两个阶段进行。首先，升级“暂存”实例，这样，您就能够测试新功能并在需要时调整配置。随后将升级“生产”实例。

所有发行日期都可能会发生更改：请定期访问此页面以检查更新。在下面指定的时间段内，将分批进行环境更新。具体日期会通过电子邮件发送给每位客户。

## 版本 24.2 - 2024 夏季版 {#release-24-2-release}

当暂存环境升级启动时，有关此版本的详细信息可在[发行说明](release-notes.md)中获取。

<table>
 <thead>
  <tr>
   <th> 环境 </th>
   <th> 有限发布版 </th>
   <th> 正式发布版 </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>暂存 </td>
   <td>2024 年 8 月 6 日至 13 日 </td>
   <td>2025 年 - 日期待定</td>
  </tr>
  <tr>
   <td>生产 </td>
   <td>2024 年 8 月 20 日至 27 日 </td>
   <td>2025 年 - 日期待定</td>
  </tr>
 </tbody>
</table>

## 问题与回答(&amp;A) {#questions-and-answers}

**问：受影响的范围包括？**

答：[发行说明](../../rn/using/release-notes.md)中列出了更改，包括相关文档的链接。Adobe 还建议查阅[已弃用和已删除的功能页面](../../rn/using/deprecated-features.md)。新版本会在 Stage 环境升级的日期提供这些页面。

**问：采用什么验证流程？**

答：升级 Stage 阶段的实例时，Adobe 建议验证您的流程和使用案例是否能使用此新版本正常工作，并向 [Adobe 客户服务](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html)报告任何问题。

**问：在升级过程中是否可以访问实例？**

答：不行。在实例升级过程中，可能有几分钟无法访问数据库。所有流程都会自动重新启动。

**问：是否会继续发送消息？**

答：不会。有几分钟不会发送消息。升级完成后，进程会自动重新启动。

**问：工作流是否会继续运行并发送投放？**

答：不会。在版本升级的过程中，工作流服务器和 MTA 都会停止。因此，在几分钟内，不会运行工作流，也不会发送投放。无需执行任何操作：一旦实例升级完成，工作流将立即重新启动。

**问：在升级过程中，消息中的跟踪链接是否仍然有效？**

答：是的，它们仍然有效。升级期间无法发送新电子邮件，但已发送电子邮件中包含的跟踪链接可正常使用。

**问：如何知晓升级已完成？**

答：登录到 Campaign 时，将显示最新版本发行说明弹出窗口。

如有其他问题，请联系 [ Adobe 客户服务](https://helpx.adobe.com/cn/enterprise/using/support-for-experience-cloud.html)。
