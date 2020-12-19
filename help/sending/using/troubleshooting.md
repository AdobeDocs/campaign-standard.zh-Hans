---
solution: Campaign Standard
product: campaign
title: Adobe Campaign Standard可交付性问题疑难解答
description: 了解在遇到Adobe Campaign Standard的可交付性问题时要做什么。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 1%

---


# 故障排除{#troubleshooting}

您是否遇到交付能力问题？ 您可以在此处找到解决方案。

## ISP {#same-error-for-an-isp}的错误消息相同

**为什么对于特定ISP，我始终收到相同的错误消息？**

如果您始终收到与ISP相同的错误消息，则ISP可能已检测到您的电子邮件或IP存在错误。 执行以下建议：
* 检查您是否收到链接到不存在的电子邮件地址的大部分故障（**用户未知**&#x200B;故障）。
* 更新订阅表单以检测输入的域名中的任何错误(例如：gmaul.com或yaho.com)。
* 如果您注意到错误消息被声明为垃圾邮件或消息被持续阻止的错误，请尝试排除在目标过去12个月中未打开或单击某封邮件的收件人。

如果问题仍然存在，请与商业或可交付性服务或Adobe Campaign支持联系。

## 阻止列表与隔离{#denylist-versus-quarantine}

* **电子邮件地址与隔离电子邮件地阻止列表址之间有何差异？**

   * 状态&#x200B;**[!UICONTROL On denylist]**&#x200B;是反馈循环的结果（当人员将邮件报告为垃圾邮件时）。

   * 状态&#x200B;**[!UICONTROL Quarantined]**&#x200B;是软弹回或硬弹回的结果。
   有关更多信息，请参阅[此章节](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)。

* **不同的隔离错误原因意味着什么？**

   以下是10个可能的原因：未定义、用户未知、无效域、地址、拒阻止列表绝、忽略错误、不可到达、禁用帐户、邮箱已满、未连接。

   有关此方面的详细信息，请参阅[了解隔离管理](../../sending/using/understanding-quarantine-management.md)。

## 正在从阻止列表{#removing-from-denylist}删除

* **我的一个收件人被误阻止列表加到。如何从阻止列表卡中删除它们，以便开始再次发送消息？**

   * 转至&#x200B;**[!UICONTROL Administration > Channels > Quarantines > Addresses]**。
   * 在相应记录的详细信息中，将&#x200B;**[!UICONTROL Status]**&#x200B;字段的值设置为&#x200B;**[!UICONTROL Valid]**。
   * 保存记录。

* **如何确定我的IP是否在阻止列表?如何从中删除我的IP阻止列表?**

   要检查您的IP地址是否阻止列表处于状态，您可以使用各个网站验证它，例如：
   * [MX工具箱](https://mxtoolbox.com/)
   * [我的IP地址是什么](https://whatismyipaddress.com)

   通常，IP地址检查的结果将返回一个列表，其中包阻止列表含的详细信息以及阻止IP地址的网站的名称。

   通过单击相应的链接，您可以访问网站详细信息。

   然后，您可以请求从添加IP地址到其的网站中取消列出您的网阻止列表站。

   >[!NOTE]
   >
   >除名过程可能因网站而异。 某些站点需要您创建帐户，而其他站点只需要您提供IP地址。
