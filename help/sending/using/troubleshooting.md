---
title: Adobe Campaign standard中的交付性问题疑难解答
description: 了解在遇到Adobe Campaign standard的可交付性问题时要做什么。
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: fc9c6371732aa0eba9e675d2709cd62c25b27b96

---


# 故障排除{#troubleshooting}

您是否遇到可交付性问题？ 您可以在此处找到解决方案……

**为什么对于特定ISP，我始终会收到相同的错误消息？**

如果ISP始终收到相同的错误消息，则ISP可能已检测到您的电子邮件或IP存在错误。 执行以下建议：
* 检查您是否收到链接到不存在的电子邮件地址的大比例故障(用&#x200B;**户未知故障** )。
* 更新订阅表单以检测所输入的域名中的任何错误(例如：gmaul.com或yaho.com)。
* 如果您注意到错误消息被声明为垃圾邮件或您的消息经常被阻止的错误，请尝试排除在目标位置最近12个月中未打开或单击您的某封邮件的收件人。

如果问题仍然存在，请与商业类或可交付性服务或Adobe Campaign支持联系。

**列入黑名单的电子邮件地址与隔离的电子邮件地址之间有何区别？**

状态是 **[!UICONTROL Blacklisted]** 反馈循环的结果（当人员将消息报告为垃圾邮件时）。

状态 **[!UICONTROL Quarantined]** 是软弹回或硬弹回的结果。

**不同的隔离错误原因意味着什么？**

以下是10个可能的原因：未定义，用户未知，无效域，黑名单地址，拒绝，错误被忽略，无法访问，帐户禁用，邮箱已满，未连接。

有关此方面的详细信息，请参 [阅了解隔离管理](../../sending/using/understanding-quarantine-management.md)。

**我的一个收件人被错误列入黑名单。 我如何将其解除黑名单，以便重新发送消息？**

* 转到 **[!UICONTROL Administration > Channels > Quarantines > Addresses]**。
* 在相应记录的详细信息中，将字段的值设 **[!UICONTROL Status]** 置为 **[!UICONTROL Valid]**。
* 保存记录。

**如何确定我的IP是否被列入黑名单？ 如何取消IP黑名单？**

要检查您的IP地址是否列入黑名单，您可以使用各个网站验证它：
* https://mxtoolbox.com/
* https://whatismyipaddress.com/blacklist-check
* http://www.blacklistalert.org/

通常，IP地址检查的结果将返回一个列表，其中包含黑名单的详细信息以及列入IP地址黑名单的网站的名称。

通过单击链接，您可以访问网站详细信息。

然后，您可以请求从列入IP地址黑名单的网站中取消列出您的网站。

除名过程可能因网站而异。 某些站点需要您创建帐户，而其他站点只需要您提供IP地址。
