---
title: 测试和发送快速入门
description: 准备、测试、计划、发送和监控您的消息。
audience: sending
content-type: reference
topic-tags: about-sending-messages-with-campaign
role: User
level: Intermediate
exl-id: bcb28ef5-5cad-43c1-b11b-080abc791a72
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '595'
ht-degree: 15%

---

# 测试和发送快速入门 {#about-sending-messages-with-campaign}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_prepare.svg" width="60px"><p><a href="#prepare-test-send">准备和测试</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#send-track-messages">发送、监视和跟踪</a></p></td>
<td><img src="assets/do-not-localize/icon_deliverability.svg" width="60px"><p><a href="#improve-deliverability">投放能力准则</a></p></td></tr>
</table>

定义目标并创建消息内容后，您需要准备并测试投放的内容、个性化、渲染和配置。 这样，在将消息发送到主目标之前，您就可以确保一切正确。 要实现此目的，可提供多种功能，如预览、校样、电子邮件主题行测试或电子邮件渲染。

执行营销活动并发送不同消息后，使用日志监控它们以检查营销活动是否成功，并检索有关收件人的跟踪信息。

最后，利用Campaign Standard中提供的投放能力准则和工具，改进投放的消息数量并确保成功的营销活动。

![](assets/do-not-localize/how-to-video.png) [了解如何发送测试电子邮件、准备和发送视频中的电子邮件投放](#video)

## 准备和测试 {#prepare-test-send}

<img src="assets/do-not-localize/icon_prepare.svg" width="60px">

Campaign Standard **消息准备**&#x200B;分析消息的目标、个性化和有效性。 在此步骤中检测到的错误必须先更正，然后才能继续。

**使用各种** 功能预览和测试消息：发送校样以测试用户档案或目标用户档案，测试电子邮件的主题行，并检查消息的呈现情况，以确保它以最佳方式在各种Web客户端、Web邮件和设备上显示。

利用Campaign计划功能定义消息的发送时间。 例如，您可以调整收件人的时区发送方式、优化发送时间或计算发送日期。

在准备期间，使用&#x200B;**分类**&#x200B;检查消息是否有效，是否通过疲劳、控制和定位规则符合质量标准。 例如，检查电子邮件是否始终包含主题行，或从消息收件人中排除未订阅者。

阅读更多:

* [准备发送](../../sending/using/preparing-the-send.md)
* [预览消息](../../sending/using/previewing-messages.md)
* [发送校样](../../sending/using/sending-proofs.md)
* [电子邮件渲染](../../sending/using/email-rendering.md)
* [计划消息发送](../../sending/using/about-scheduling-messages.md)
* [关于类型和类型规则](../../sending/using/about-typology-rules.md)

## 发送、监视和跟踪 {#send-track-messages}

<img src="assets/do-not-localize/icon_send.svg"  width="60px">

消息准备就绪后，您可以确认向&#x200B;**发送和访问日志及报告，以监控投放**&#x200B;并衡量营销活动是否成功。 Adobe Campaign还提供电子邮件警报系统，用于跟踪投放是成功还是失败，以及隔离管理功能。

**使用会** 话和永久Cookie跟踪消息收件人的行为，以检索跟踪信息（已点击的URL、镜像页面、已打开的消息……）。

最后，您可以将Adobe Campaign配置为&#x200B;**保留通过电子邮件密送从您的平台发送的电子邮件**&#x200B;的副本。 特别是，如果贵组织需要存档所有出站电子邮件以符合要求，则可以启用此功能。

阅读更多:

* [确认发送](../../sending/using/confirming-the-send.md)
* [跟踪消息](../../sending/using/tracking-messages.md)
* [通过电子邮件密送进行归档](../../sending/using/archiving.md)
* [监测投放](../../sending/using/monitoring-a-delivery.md)
* [了解投放失败](../../sending/using/understanding-delivery-failures.md)
* [了解隔离管理](../../sending/using/understanding-quarantine-management.md)

## 投放能力准则 {#improve-deliverability}

<img src="assets/do-not-localize/icon_deliverability.svg"  width="60px">

投放能力允许测量营销活动到达收件人收件箱的成功情况，而不会出现弹回或标记为垃圾邮件。

Campaign Standard提供了多个&#x200B;**可投放性工具**&#x200B;来帮助您提高成功投放消息的数量：投放吞吐量报告、发送时间优化、消息预览、电子邮件渲染、隔离管理等。

阅读更多:

* [关于可投放性](../../sending/using/about-deliverability.md)
* [监测可投放性](../../sending/using/monitor-deliverability.md)
* [Adobe投放能力最佳实践指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=zh-Hans)
* [控制投放吞吐量](../../reporting/using/delivery-throughput.md)

## 其他资源

* [设计A/B测试电子邮件](../../channels/using/designing-an-a-b-test-email.md)
* [电子邮件入门](https://helpx.adobe.com/cn/campaign/kb/acs-get-started-with-emails.html)
* [投放最佳实践](../../sending/using/delivery-best-practices.md)
* [添加对照组](../../sending/using/control-group.md)

## 教程视频 {#video}

此视频演示如何发送测试电子邮件、准备电子邮件，然后以Campaign Standard发送电子邮件投放。

>[!VIDEO](https://video.tv.adobe.com/v/24013/)

其他Campaign Standard操作方法视频可在[此处](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=zh-Hans)获取。
