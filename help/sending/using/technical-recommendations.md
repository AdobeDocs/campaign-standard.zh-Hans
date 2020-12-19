---
solution: Campaign Standard
product: campaign
title: 为Adobe Campaign Standard提供可交付性技术建议
description: 阅读一些技术建议，以提高Adobe Campaign Standard的交付能力。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 0%

---


# 技术建议{#technical-recommendations}

下面列出了几种可用于提高交付率的技术、配置和工具。 以下是一些主要技术术语的定义。

**反向DNS**:Adobe Campaign检查是否为IP地址提供反向DNS，并且这正确地指向IP。

**MX规** 则用于控制活动MTA（邮件传输代理）向每个电子邮件域或ISP（如hotmail.com、comcast.net）发送电子邮件的速度。这些规则通常基于ISP发布的限制（例如，每个SMTP连接不包含20条以上的邮件）。

**TLS** （传输层安全性）是一种加密协议，可用于保护两个电子邮件服务器之间的连接，并保护电子邮件内容不被除预期收件人之外的任何人读取。

**SPF** （发送者策略框架）是电子邮件身份验证标准，允许域的所有者指定允许哪些电子邮件服务器代表该域发送电子邮件。此标准使用电子邮件的“返回路径”标题（也称为“信封发件人”地址）中的域。

**DKIM** （域密钥识别邮件）身份验证是SPF的后继身份验证，它使用公钥密码术，允许接收电子邮件服务器验证消息实际上是由其声称其发送的个人或实体发送的，以及消息内容是否在最初发送时（和DKIM“已签名”）和接收时间之间发生更改。此标准通常使用“发件人”或“发件人”标题中的域。

**DMARC** (基于域的邮件身份验证、报告和符合性)是最新的电子邮件身份验证形式，它依赖SPF和DKIM身份验证来确定电子邮件是否通过或失败。DMARC在两个非常重要的方面具有独特性和强大性：
* 符合性——它允许发送方指示ISP如何处理未通过身份验证的消息（例如，不接受它）。
* 报告-它向发送方提供详细报告，显示DMARC身份验证失败的所有消息，以及每个用户使用的“发件人”域和IP地址。 这允许公司识别身份验证失败且需要某种类型的“修复”（例如，将IP地址添加到其SPF记录）的合法电子邮件，以及其电子邮件域上的网络钓鱼尝试的来源和流行情况。

DMARC可以利用250ok生成的报表。

**SMTP** （简单邮件传输协议）是电子邮件传输的Internet标准。

**专用IP**:Adobe为每位客户提供专用的IP战略，增加IP，以建立信誉并优化投放性能。
