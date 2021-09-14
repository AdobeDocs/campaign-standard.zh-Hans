---
title: 在 ISP 中断后更新退回限制条件
description: 了解如何在ISP中断后更新退件资格。
audience: delivery
content-type: reference
topic-tags: monitoring-deliveries
hidefromtoc: true
exl-id: b06e9009-70c7-459f-8a9f-d5b7020d662f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 4%

---

# 在 ISP 中断后更新退回限制条件 {#update-bounce-qualification.md}

如果您没有运行最新版本的Campaign，则此部分可能适用于您。 请咨询您的Adobe Campaign代表。

## 上下文

如果ISP发生中断，则无法成功将通过Campaign发送的电子邮件发送给其收件人：这些电子邮件将被错误地标记为退回。

2020年12月，Gmail的一个全局问题导致发送给有效Gmail电子邮件地址的一些电子邮件被错误地硬退件为Gmail服务器的无效电子邮件地址，并出现以下退件响应：*&quot;550-5.1.1您尝试访问的电子邮件帐户不存在。&quot;*

Google称，导致此问题的Gmail中断和中断始于12月14日早上6:55，并于12月15日东部时间下午6:09结束。 我们的数据分析还显示，在美国东部标准时间12月16日凌晨2点06分Gmail退回量出现非常短的峰值，其中大部分发生在12月15日美国东部标准时间下午2点到下午6点30之间。

>[!NOTE]
>
>您可以在[此页面](https://www.google.com/appsstatus#hl=en&amp;v=status)上查看Google工作区状态功能板。


根据标准退回处理逻辑，Adobe Campaign会自动将这些收件人添加到隔离列表，其中&#x200B;**[!UICONTROL Status]**&#x200B;设置为&#x200B;**[!UICONTROL Quarantine]**。 要更正此问题，您需要通过查找并删除这些收件人，或将其&#x200B;**[!UICONTROL Status]**&#x200B;更改为&#x200B;**[!UICONTROL Valid]**&#x200B;来更新Campaign中的隔离表，以便夜间清理工作流将删除这些收件人。

要查找受此Gmail问题影响的收件人，或者如果在其他任何ISP中再次出现此问题，请参阅下面的说明。

## 更新流程

您需要对隔离表格运行查询，以过滤掉所有可能受中断影响的Gmail（或其他ISP）收件人，以便将他们从隔离列表中删除，并包含在将来的Campaign电子邮件投放中。

根据事件的时间范围，以下是此查询的建议准则。

>[!IMPORTANT]
>
>这些日期/时间基于东部标准时区(EST)。 请根据实例的时区进行调整。

对于隔离列表&#x200B;**[!UICONTROL Error text]**&#x200B;字段中具有SMTP退回响应信息的Campaign实例：

* **错误文本（隔离文本）** 包含“550-5.1.1您尝试访问的电子邮件帐户不存在”，而 **错误文本（隔离文本）** 包含“support.google.com”**
* **早上6点或之后** 更新状态(@lastModified):55:12/14/2020 00
* **更新状态(@lastModified)** 早6时或12/16/2020之前:00:00分

获得受影响的收件人列表后，您可以将其设置为状态&#x200B;**[!UICONTROL Valid]** ，以便通过&#x200B;**[!UICONTROL Database cleanup]**&#x200B;工作流将其从隔离列表中删除，或只从表中删除它们。

**相关主题：**
* [了解投放失败](../../sending/using/understanding-delivery-failures.md)
* [退回邮件鉴别](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)
