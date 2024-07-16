---
title: 对Adobe Campaign Standard中的可投放性问题进行故障诊断
description: 了解在使用Adobe Campaign Standard时遇到可投放性问题时该怎么做。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: User
level: Intermediate
exl-id: 0470b986-c00a-4441-8621-82c7112a9953
source-git-commit: 449187bba167f9ce00e644d44a124b36030ba001
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 1%

---

# 故障排除{#troubleshooting}

您是否遇到过可投放性问题？ 您可以在此处找到解决方案。

## ISP的同一错误消息 {#same-error-for-an-isp}

**为什么我总是收到针对特定ISP的相同错误消息？**

如果您总是收到与ISP相同的错误消息，则您的电子邮件或IP可能被ISP检测到为故障。 执行以下建议：

* 检查您是否收到大量与不存在电子邮件地址关联的故障（**用户未知**&#x200B;个故障）。
* 更新您的订阅表单，以检测输入的域名中是否有任何错误(例如：gmaul.com或yaho.com)。
* 如果您发现错误，指出您的邮件被声明为垃圾邮件，或您的邮件被持续阻止，请尝试排除过去12个月内未打开或单击您邮件之一的收件人，使其离开目标。

如果问题仍然存在，请联系商业或可投放性服务或Adobe Campaign支持。

## 阻止列表与隔离 {#denylist-versus-quarantine}

* **阻止列表的电子邮件地址与隔离的电子邮件地址有何区别？**

   * 状态&#x200B;**[!UICONTROL On denylist]**&#x200B;是[反馈循环](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops)的结果（当某人报告邮件为垃圾邮件时）。

   * 状态&#x200B;**[!UICONTROL Quarantined]**&#x200B;是软退回或硬退回的结果。

  有关更多信息，请参阅[此章节](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)。

* **不同的隔离错误原因意味着什么？**

  以下是10个可能的原因：未定义、用户未知、域无效、阻止列表时的地址、已拒绝、错误已忽略、无法访问、帐户已禁用、邮箱已满、未连接。

  有关此内容的详细信息，请参阅[了解隔离管理](../../sending/using/understanding-quarantine-management.md)。

## 从阻止列表中删除 {#removing-from-denylist}

* **我的一名收件人被错误地添加到阻止列表中。 如何从阻止列表中删除这些邮件，以便我能够再次向他们发送邮件？**

   * 转到&#x200B;**[!UICONTROL Administration > Channels > Quarantines > Addresses]**。
   * 在对应的记录的详细信息中，将&#x200B;**[!UICONTROL Status]**&#x200B;字段的值设置为&#x200B;**[!UICONTROL Valid]**。
   * 保存记录。

* 列入阻止列表 **如何确定我的IP是否处于状态？ 如何从阻止列表中删除我的IP？**

  要检查您的IP地址是否处于阻止列表状态，您可以使用各种网站对其进行验证，例如：
   * [MX工具箱](https://mxtoolbox.com/)
   * [我的IP地址是什么](https://whatismyipaddress.com)

  列入阻止列表通常，IP地址检查的结果将返回一个列表，其中包含IP地址的详细信息，以及阻止IP地址的网站的名称。

  通过单击相应的链接，您可以访问网站详细信息。

  列入阻止列表然后，您可以请求将您的网站从将IP地址添加到其的网站中除名。

  >[!NOTE]
  >
  >除名过程可能因网站而异。 有些站点要求您创建帐户，而有些站点仅要求您提供IP地址。
