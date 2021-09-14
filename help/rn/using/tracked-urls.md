---
title: 跟踪的 URL 签名问题
description: 跟踪的 URL 签名问题
hidefromtoc: true
hide: true
exl-id: 8c2725a8-2c3a-448a-8c04-c0c2a5950574
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 100%

---

# 跟踪的 URL 签名问题 {#tracked-urls}

在最近的更改后，由 Campaign 发送的跟踪的 URL 可能会失效。某些邮箱可能比其他邮箱受到的影响更大，因为某些公司具有特定的安全工具，这些工具可能会影响链接并更改 URL 签名机制。

因此，Adobe 决定禁用跟踪链接的签名机制。此过程修复了所有跟踪链接。

请注意，退订链接可能会像任何其他链接一样失效，其频率在不同主机上是可变的，但小于 1%。

**您是否受影响？**

某些 Campaign Standard 用户会受到影响，因为跟踪电子邮件中链接的签名机制已引入到 [Campaign Standard 20.4](release-notes-2020.md#release-20-4---october-2020) - 2020 年 10 月版中，并且默认情况下对所有客户都启用了该机制。

**如何更新？**

Adobe 将会很快协助您更新配置。您将收到一封包含升级时间线的电子邮件通知。

**会有什么影响？**

维护工作最长需要 25 分钟的停机时间，在此期间，所有投放、跟踪链接和 API 调用都无法工作。

完成更新后，所有链接都会按预期工作。

>[!NOTE]
>
>有关这些更改的任何问题，请联系 [Adobe 客户关怀](https://helpx.adobe.com/cn/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html)。
