---
title: 使用Adobe Campaign Standard启动新平台
description: 了解如何使用Adobe Campaign Standard建立新平台，同时保持您的域名和IP地址声誉。
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
source-git-commit: 89965d859986b9176de6b6bf96df1fbbb89b5b8f

---


# 启动新平台{#starting-new-platform}

维护您的域名和IP地址声誉是必不可少的。 以下是建立新平台的一些建议。

开始在新平台上发送电子邮件是一个敏感步骤，因为该平台没有任何使用历史记录和信誉（当发送的IP从未用于此目的时）。 ISP自然会对从未用来发送电子邮件的IP地址产生怀疑，而且突然开始发送大量电子邮件流量。 实际上，垃圾邮件发送者通常使用“未知”IP地址（即从未列入黑名单的地址）在检测前发送尽可能多的邮件。

在生产阶段开始时，您不能期望在输出方面达到操作速度。 此外，您不应尝试以此速率发送消息，因为这可能导致ISP阻止发送地址并严重危害启动阶段的其余部分。

首次使用地址列表（可能未完全限定）时，通常会启动平台。 如果发送到无效地址或蜜罐地址，这会降低平台的声誉。 如果您有无效地址列表，则在首次发送之前将其导入隔离表(**[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Quarantines]** &gt; **[!UICONTROL Addresses]**)符合您的最大利益。 尽管如此，如果您希望重新指定无效地址，则最好在平台信誉建立后再逐位执行此操作，以便随着时间的推移“稀释”使用不良地址。

总结在启动时应遵循的原则：
* **将专用子域委派到Adobe** ，该子域特定于从Adobe发送的电子邮件营销活动
* **将无效／非活动地址导入隔离表** （如果您有此信息）
* **限制交付吞吐量** (技术设置：限制匹配的数目)
* **逐渐增加发送的卷**:不要从一开始就瞄准整个数据库，而是每次发送时增加一个额外的列表部分；这应允许您在每个步骤中增加音量，同时降低无效地址的总体速率
* **定期发送消息**:从某种程度上讲，最好定期发送小照片，而不是偶尔发送大型营销活动
* **密切监视交付报告**:高错误指示器可能意味着技术设置配置错误。
