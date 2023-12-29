---
title: 在 ISP 中断后更新退回限制条件
description: 了解如何在ISP中断后更新退回限制条件。
audience: delivery
hidefromtoc: true
exl-id: b06e9009-70c7-459f-8a9f-d5b7020d662f
source-git-commit: f81b8a3b076a6e29b697f21ea4d99fa7d5b6788c
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 2%

---

# 在ISP中断后更新退回限制条件 {#update-bounce-qualification.md}

## 上下文

如果ISP发生中断，通过Campaign发送的电子邮件无法成功发送给收件人：这些电子邮件将被错误标记为退回。

2020年12月，Gmail的一个全球问题导致发送到有效Gmail电子邮件地址的一些电子邮件被错误地硬退回，作为Gmail服务器的无效电子邮件地址，并返回以下响应： *“550-5.1.1您尝试访问的电子邮件帐户不存在。”*

Google已声明，导致此问题的Gmail中断和中断从12月14日早上6:55开始并在12月15日晚上6:09 EST结束。 我们的数据分析还显示，Gmail在12月16日凌晨2:06点（东部标准时间）的跳出率出现了非常短暂的峰值，大多数跳出发生在12月15日下午2:00（东部标准时间）到下午6:30（东部标准时间）之间。

>[!NOTE]
>
>您可以在上查看Google工作区状态功能板 [此页面](https://www.google.com/appsstatus#hl=en&amp;v=status).


根据标准退回处理逻辑，Adobe Campaign会使用自动将这些收件人添加到隔离列表 **[!UICONTROL Status]** 设置 **[!UICONTROL Quarantine]**. 要更正此问题，您需要通过查找并移除这些收件人或更改其在Campaign中的隔离表来更新隔离表 **[!UICONTROL Status]** 到 **[!UICONTROL Valid]** 以便“夜间清理”工作流会删除它们。

要查找受此Gmail问题影响的收件人，或者如果这种情况再次发生在任何其他ISP身上，请参阅下面的说明。

## 更新流程

您需要对隔离表运行查询，以筛选掉所有可能受服务中断影响的Gmail（或其他ISP）收件人，以便将其从隔离列表中删除，并包含在将来的Campaign电子邮件投放中。

根据事件的时间范围，以下是此查询的建议准则。

>[!IMPORTANT]
>
>这些日期/时间基于东部标准时区(EST)。 请根据实例的时区进行调整。

对于包含SMTP退回响应信息的Campaign实例，请参阅 **[!UICONTROL Error text]** 隔离列表的字段：

* **错误文本（隔离文本）** 包含“550-5.1.1您尝试访问的电子邮件帐户不存在”并且 **错误文本（隔离文本）** 包含“support.google.com”**
* **更新状态(@lastModified)** 2020年12月14日或之后6:55:上午00
* **更新状态(@lastModified)** 2020年12月16日或之前6:00:上午00

获得受影响的收件人列表后，您可以将其设置为状态 **[!UICONTROL Valid]** 因此它们将被从隔离列表中删除 **[!UICONTROL Database cleanup]** 工作流，或者只是从表中删除它们。

**相关主题：**
* [了解投放失败](../../sending/using/understanding-delivery-failures.md)
* [退回邮件鉴别](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)
