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
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 1%

---

# 故障排除{#troubleshooting}

您是否遇到过可投放性问题？ 您可以在此处找到解决方案。

## ISP出现相同的错误消息 {#same-error-for-an-isp}

**为什么我会始终收到针对特定ISP的相同错误消息？**

如果您总是收到与ISP相同的错误消息，则您的电子邮件或IP可能被ISP检测到有故障。 执行以下建议：
* 检查您是否收到大量与不存在电子邮件地址关联的故障(**用户未知** 失败)。
* 更新您的订阅表单以检测输入的域名中是否有任何错误(例如：gmaul.com或yaho.com)。
* 如果您注意到声明您的邮件被声明为垃圾邮件的错误，或您的邮件被持续阻止，请尝试排除过去12个月内未从目标位置打开或单击某封邮件的收件人。

如果问题仍然存在，请联系商业或可投放性服务或Adobe Campaign支持。

## 阻止列表与隔离 {#denylist-versus-quarantine}

* **阻止列表上的电子邮件地址与隔离的电子邮件地址之间有何区别？**

   * 状态 **[!UICONTROL On denylist]** 是 [反馈环](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops) （当人员将消息报告为垃圾邮件时）。

   * 状态 **[!UICONTROL Quarantined]** 是软退回或硬退回的结果。
   有关更多信息，请参阅[此章节](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)。

* **不同的隔离错误原因意味着什么？**

   以下是10个可能的原因：未定义、用户未知、域无效、阻止列表地址、被拒绝、错误被忽略、无法访问、帐户已禁用、邮箱已满、未连接。

   有关此内容的更多信息，请参阅 [了解隔离管理](../../sending/using/understanding-quarantine-management.md).

## 从阻止列表中删除 {#removing-from-denylist}

* **我的一名收件人被错误地添加到阻止列表中。 如何将其从阻止列表中删除，以便可以再次向他们发送消息？**

   * 转到 **[!UICONTROL Administration > Channels > Quarantines > Addresses]**.
   * 在对应的记录的详细信息中，设置 **[!UICONTROL Status]** 字段至 **[!UICONTROL Valid]**.
   * 保存记录。

* **如何确定我的IP之一是否处于阻止列表状态？ 阻止列表如何从中删除我的IP？**

   要检查您的IP地址是否处于阻止列表状态，您可以使用各种网站对其进行验证，例如：
   * [MX Toolbox](https://mxtoolbox.com/)
   * [我的IP地址是什么](https://whatismyipaddress.com)

   阻止列表通常，IP地址检查的结果将返回一个列表，其中包含的详细信息以及阻止IP地址的网站的名称。

   通过单击相应的链接，您可以访问网站详细信息。

   阻止列表然后，您可以请求从将IP地址添加到其的网站中取消列出您的网站。

   >[!NOTE]
   >
   >除名过程可能因网站而异。 有些站点要求您创建帐户，而有些站点则要求您提供IP地址。
