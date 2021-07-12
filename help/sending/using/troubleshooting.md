---
solution: Campaign Standard
product: campaign
title: 对Adobe Campaign Standard中的投放能力问题进行故障诊断
description: 了解在Adobe Campaign Standard遇到可投放性问题时要执行的操作。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: 可投放性
role: User
level: Intermediate
exl-id: 0470b986-c00a-4441-8621-82c7112a9953
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 1%

---

# 故障排除{#troubleshooting}

您遇到投放能力问题吗？ 你可以在这里找到解决方案。

## ISP的相同错误消息 {#same-error-for-an-isp}

**为什么对于特定ISP，我始终会收到相同的错误消息？**

如果ISP始终收到相同的错误消息，则ISP可能会检测到您的电子邮件或IP存在错误。 执行以下建议：
* 检查您是否收到与不存在的电子邮件地址相关的大量失败（**用户未知**&#x200B;失败）。
* 更新订阅表单以检测输入的域名中是否存在任何错误(例如：gmaul.com或yaho.com)。
* 如果您发现错误，指出您的消息被声明为垃圾邮件，或您的消息被持续阻止，请尝试排除在目标位置最近12个月内未打开或单击其中一条消息的收件人。

如果问题仍然存在，请联系商业或可投放性服务或Adobe Campaign支持。

## 阻止列表隔离 {#denylist-versus-quarantine}

* **“”上的电子邮件地址与隔离的阻止列表电子邮件地址之间有何区别？**

   * 状态&#x200B;**[!UICONTROL On denylist]**&#x200B;是[反馈循环](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops)（当某人将消息报告为垃圾邮件时）的结果。

   * 状态&#x200B;**[!UICONTROL Quarantined]**&#x200B;是软退件或硬退件的结果。
   有关更多信息，请参阅[此章节](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)。

* **不同的隔离错误原因意味着什么？**

   以下是10个可能的原因：未定义、用户未知、域无效、地址、拒阻止列表绝、错误忽略、不可访问、帐户已禁用、邮箱已满、未连接。

   有关更多信息，请参阅[了解隔离管理](../../sending/using/understanding-quarantine-management.md)。

## 从阻止列表中删除 {#removing-from-denylist}

* **我的一个收件人被错误地添阻止列表加到中。如何从中删阻止列表除它们，以便能够再次发送消息？**

   * 转到&#x200B;**[!UICONTROL Administration > Channels > Quarantines > Addresses]**。
   * 在相应记录的详细信息中，将&#x200B;**[!UICONTROL Status]**&#x200B;字段的值设置为&#x200B;**[!UICONTROL Valid]**。
   * 保存记录。

* **如何确定我的一个IP是否处于状阻止列表态？如何从中删除我的IP阻止列表?**

   要检查您的IP地址是否已，您可阻止列表以使用各种网站来验证它，例如：
   * [MX工具箱](https://mxtoolbox.com/)
   * [我的IP地址是什么](https://whatismyipaddress.com)

   通常，IP地址检查结果将返回一个列表，其中包含的详细信阻止列表息以及阻止IP地址的网站名称。

   通过单击相应的链接，可访问网站详细信息。

   然后，您可以请求将您的网站从添加了IP地址的网站中除阻止列表名。

   >[!NOTE]
   >
   >除名过程可能因网站而异。 有些网站需要您创建帐户，而另一些网站则只需要您提供IP地址。
