---
solution: Campaign Standard
product: campaign
title: 解决Adobe Campaign Standard中的可交付性问题
description: 了解在遇到Adobe Campaign Standard的可交付性问题时要做什么。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: fb9a6218bb754f803affde1fdf6c6fc01570126f
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 2%

---


# 故障排除{#troubleshooting}

您是否遇到交付能力问题？ 您可以在此处找到解决方案。

## ISP {#same-error-for-an-isp}的相同错误消息

**为什么我总是收到与特定ISP相同的错误消息？**

如果ISP始终收到相同的错误消息，则ISP可能已检测到您的电子邮件或IP存在错误。 执行以下建议：
* 检查您是否收到链接到不存在的电子邮件地址的大部分故障（**用户未知**&#x200B;故障）。
* 更新您的订阅表单以检测输入的域名中的任何错误(例如：gmaul.com或yaho.com)。
* 如果您注意到声明您的邮件被声明为垃圾邮件或您的邮件经常被阻止的错误，请尝试排除在目标的过去12个月中未打开或单击您的某封邮件的收件人。

如果问题仍然存在，请联系商业或交付服务或Adobe Campaign支持。

## 阻止列表与隔离{#denylist-versus-quarantine}

* **时的电子邮件地址与隔离的电阻止列表子邮件地址有何区别？**

   * 状态&#x200B;**[!UICONTROL On denylist]**&#x200B;是[反馈循环](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops)（当人将消息报告为垃圾邮件时）的结果。

   * 状态&#x200B;**[!UICONTROL Quarantined]**&#x200B;是软弹回或硬弹回的结果。
   有关更多信息，请参阅[此章节](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)。

* **不同的隔离错误原因意味着什么？**

   以下是10个可能的原因：未定义、用户未知、无效域、地址、拒阻止列表绝、错误忽略、不可到达、帐户禁用、邮箱已满、未连接。

   有关此方面的详细信息，请参阅[了解隔离管理](../../sending/using/understanding-quarantine-management.md)。

## 正在从阻止列表{#removing-from-denylist}中删除

* **我的一个收件人被误加阻止列表入。如何从中删阻止列表除它们，以便能够开始再次发送消息？**

   * 转到&#x200B;**[!UICONTROL Administration > Channels > Quarantines > Addresses]**。
   * 在相应记录的详细信息中，将&#x200B;**[!UICONTROL Status]**&#x200B;字段的值设置为&#x200B;**[!UICONTROL Valid]**。
   * 保存记录。

* **如何确定我的IP是否在阻止列表?如何从中删除我的阻止列表IP?**

   要检查您的IP地址是否阻止列表处于状态，您可以使用各个网站验证它，例如：
   * [MX工具箱](https://mxtoolbox.com/)
   * [我的IP地址是什么](https://whatismyipaddress.com)

   通常，IP地址检查的结果将返回一个列表，其中包含的详细信阻止列表息以及阻止IP地址的网站的名称。

   通过单击相应的链接，您可以访问网站详细信息。

   然后，您可以请求从添加IP地址到其的网站中取消列出您的网阻止列表站。

   >[!NOTE]
   >
   >除名过程可能因网站而异。 某些站点需要您创建帐户，而其他站点只需要您提供IP地址。
