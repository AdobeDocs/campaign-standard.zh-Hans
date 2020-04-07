---
title: 关于使用 Campaign 发送消息
description: 发现测试和发送消息的不同步骤。
page-status-flag: never-activated
uuid: 58666444-6e7c-4049-b2d2-8b26eabf5a82
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: about-sending-messages-with-campaign
discoiquuid: ae2eba1c-24ad-4839-afa9-5a2975570d9b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e6c43770755e59bf2a2d49540a052ac0bd2a2438

---


# 关于使用 Campaign 发送消息{#about-sending-messages-with-campaign}

定义目标并创建消息内容后，您需要测试和批准内容、个性化、渲染和配置，并确保在将消息发送到主目标之前一切正确。

为此，最佳实践是：

* 准备发送：此步骤允许您转到分析和准备要发送的消息。 消息准备分析消息的目标、个性化和有效性。 在此步骤中检测到的错误必须经过更正，才能继续执行。 您可以根据需要多次启动消息准备。 For more on message preparation, refer to [this section](../../sending/using/preparing-the-send.md).

   >[!NOTE]
   >
   >您可以设置全局交叉渠道疲劳规则，该规则将自动从活动中排除过度激励的用户档案。 请参阅 [疲劳规则](../../sending/using/fatigue-rules.md)。

* 使用测试预览消息。 For more on previewing messages, refer to [this section](../../sending/using/previewing-messages.md).
* 发送验证以测试消息。 For more on proofs, refer to [this  section](../../sending/using/sending-proofs.md).
* 检查消息呈现：确保您的消息以最佳方式显示在各种Web客户端、Web邮件和设备上。 在本节中进一步了解电子邮件 [呈现](../../sending/using/email-rendering.md)。

然后，您可以：

* 计划发送：您可以定义消息的发送时间。 例如，您可以在收件人的时区调整发送、优化发送时间或计算发送日期。 在本节中了解 [更多信息](../../sending/using/about-scheduling-messages.md)。
* 发送消息：消息准备就绪后，您可以开始发送。 访问日志和报告随后可用于监视消息投放并衡量活动的成功程度。 Adobe Campaign还提供电子邮件警报系统，以跟踪投放成功或失败。 在本页了解 [更多信息](../../sending/using/confirming-the-send.md)。

## 相关主题

| 有用页面 | 其他资源 |
|---|---|
| [优化您的交付能力](../../sending/using/about-deliverability.md) | [疲劳管理](../../sending/using/fatigue-rules.md) |
| [监控投放](../../audiences/using/creating-profiles.md) | [设计A/B测试电子邮件](../../channels/using/designing-an-a-b-test-email.md) |
| [在失败时接收通知](../../sending/using/receiving-alerts-when-failures-happen.md) | [监控投放](../../sending/using/monitoring-a-delivery.md) |
| [构建对照组](../../automating/using/workflow-control-group.md) | [在失败时接收通知](../../sending/using/receiving-alerts-when-failures-happen.md) |
| [控制投放吞吐量](../../reporting/using/delivery-throughput.md) | [监控投放](../../sending/using/monitoring-a-delivery.md) |