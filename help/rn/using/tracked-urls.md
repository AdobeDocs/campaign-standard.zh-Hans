---
solution: Campaign Standard
product: campaign
title: 跟踪的URL签名问题
description: 跟踪的URL签名问题
translation-type: tm+mt
source-git-commit: 830c003e36cec41e5cf480f66812900312609e9f
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 3%

---


# 跟踪的URL签名问题{#tracked-urls}

在最近的更改后，由活动发送的跟踪URL可能会失败。 某些邮箱可能比其他邮箱受到的影响更大，因为某些公司具有特定的安全工具，这些工具可能会影响链接并更改URL签名机制。

因此，Adobe决定禁用跟踪链接的签名机制。 此过程修复了所有跟踪链接。

请注意，退订链路可能会像任何其他链接一样失败，其频率从主机到主机是可变的，但小于1%。

**您是否受影响？**

某些Campaign Standard用户会受到影响，因为[Campaign Standard20.4](release-notes-2020.md#release-20-4---october-2020) - 2020年10月 — 中引入了跟踪电子邮件中链接的签名机制，并且默认情况下对所有客户都启用了该机制。

**如何更新？**

Adobe很快将与您一起更新您的配置。 您将收到一封包含升级时间线的电子邮件通知。

**影响是什么？**

维护最长需要25分钟的停机时间，在此期间，所有投放、跟踪链接和API调用都将无效。

完成更新后，所有链接都会按预期工作。

>[!NOTE]
>
>有关这些更改的任何问题，请联系[Adobe客户关怀](https://helpx.adobe.com/cn/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html)。

