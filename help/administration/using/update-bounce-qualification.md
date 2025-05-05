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

# 在ISP中断后更新退回限制条件{#update-bounce-qualification.md}

## 上下文

如果ISP发生中断，通过Campaign发送的电子邮件无法成功发送给收件人：这些电子邮件将被错误标记为退回。

2020年12月，Gmail的一个全局问题导致发送到有效Gmail电子邮件地址的某些电子邮件被错误地硬退回，作为Gmail服务器的无效电子邮件地址，并返回以下响应： *&quot;550-5.1.1您尝试访问的电子邮件帐户不存在。&quot;*

Google已声明，导致此问题的Gmail中断和中断从12月14日早上6:55开始并在12月15日晚上6:09 EST结束。 我们的数据分析还显示，Gmail在12月16日凌晨2:06点（东部标准时间）的跳出率出现了非常短暂的峰值，大多数跳出发生在12月15日下午2:00（东部标准时间）到下午6:30（东部标准时间）之间。

>[!NOTE]
>
>您可以在[此页面](https://www.google.com/appsstatus#hl=en&amp;v=status)上查看Google Workspace状态仪表板。


根据标准退回处理逻辑，Adobe Campaign已使用&#x200B;**[!UICONTROL Status]**&#x200B;设置&#x200B;**[!UICONTROL Quarantine]**&#x200B;将这些收件人自动添加到隔离列表。 要更正此问题，您需要在Campaign中更新隔离表，方法是查找并移除这些收件人，或将其&#x200B;**[!UICONTROL Status]**&#x200B;更改为&#x200B;**[!UICONTROL Valid]**，以便夜间清理工作流将移除这些收件人。

要查找受此Gmail问题影响的收件人，或者如果这种情况再次发生在任何其他ISP身上，请参阅下面的说明。

## 更新流程

您需要对隔离表运行查询，以筛选掉所有可能受服务中断影响的Gmail（或其他ISP）收件人，以便将其从隔离列表中删除，并包含在将来的Campaign电子邮件投放中。

根据事件的时间范围，以下是此查询的建议准则。

>[!IMPORTANT]
>
>这些日期/时间基于东部标准时区(EST)。 请根据实例的时区进行调整。

对于隔离列表的&#x200B;**[!UICONTROL Error text]**&#x200B;字段中包含SMTP退回响应信息的Campaign实例：

* **错误文本（隔离文本）**&#x200B;包含“550-5.1.1您尝试访问的电子邮件帐户不存在”以及&#x200B;**错误文本（隔离文本）**&#x200B;包含“support.google.com”**
* 上午12/14/2020 6:55:00时或之后的&#x200B;**更新状态(@lastModified)**
* **在上午12/16/2020 6:00:00或之前更新状态(@lastModified)**

在获得受影响的收件人列表后，您可以将他们的状态设置为&#x200B;**[!UICONTROL Valid]**，以便通过&#x200B;**[!UICONTROL Database cleanup]**&#x200B;工作流将其从隔离列表中删除，或者只是从表中删除他们。

**相关主题：**
* [了解投放失败](../../sending/using/understanding-delivery-failures.md)
* [退回邮件鉴别](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)
