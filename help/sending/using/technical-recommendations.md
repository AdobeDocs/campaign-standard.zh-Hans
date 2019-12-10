---
title: Adobe Campaign standard的可交付性技术建议
description: 阅读一些技术建议，以改进Adobe Campaign Standard的可交付性。
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
source-git-commit: 44049443f8028ed26089ee0d49944ebac6a62111

---


# 技术建议{#technical-recommendations}

此外，下面列出了几种可用于提高交付率的技术、配置和工具。

以下是一些主要技术术语的定义。

**反向DNS** Adobe Campaign检查是否为IP地址提供了反向DNS，并且这会正确地指向IP。

**MX规则** MX规则用于控制Campaign MTA（消息传输代理）向每个电子邮件域或ISP（例如hotmail.com、comcast.net）发送电子邮件的速度。 这些规则通常基于ISP发布的限制（例如，每个SMTP连接不包含超过20条消息）。

**TLS**（传输层安全）是一种加密协议，可用于保护两个电子邮件服务器之间的连接并保护电子邮件内容不被目标收件人以外的任何人读取。

**SPF** SPF（发送者策略框架）是电子邮件身份验证标准，允许域的所有者指定允许哪些电子邮件服务器代表该域发送电子邮件。 此标准使用电子邮件的“Return-Path”标题（也称为“信封发件人”地址）中的域。

**DKIM** DKIM（域密钥标识邮件）身份验证是SPF的继承者，并使用公钥密码术，允许接收电子邮件服务器确认消息实际上是由其声称其被发送的个人或实体发送的，以及消息内容在最初发送（和DKIM“已签名”）和接收时间之间是否发生了更改。 此标准通常使用“发件人”或“发送者”标题中的域。

**DMARC** DMARC（基于域的消息身份验证、报告和符合性）是最新的电子邮件身份验证形式，它依赖SPF和DKIM身份验证来确定电子邮件是否通过。 DMARC在两个非常重要的方面具有独特性和强大性：
* 符合性——它允许发送方指示ISP如何处理未通过身份验证的消息（例如，不接受它）。
* 报告——它向发送方提供详细报告，其中显示DMARC验证失败的所有消息，以及每个消息使用的“发件人”域和IP地址。 这使公司能够识别身份验证失败且需要某种类型的“修复”（例如，将IP地址添加到其SPF记录）的合法电子邮件，以及其电子邮件域上网络钓鱼尝试的来源和流行情况。

DMARC可以利用250ok生成的报表。

**SMTP** SMTP（简单邮件传输协议）是电子邮件传输的Internet标准。

**专用IP** adobe为每位客户提供专用IP战略，以提升声誉和优化交付性能。
