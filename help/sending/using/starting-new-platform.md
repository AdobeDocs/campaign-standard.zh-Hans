---
solution: Campaign Standard
product: campaign
title: 与Adobe Campaign Standard建立新平台
description: 了解如何建立新平台，同时保持您在Adobe Campaign Standard的域和IP地址信誉。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 2%

---


# 启动新平台{#starting-new-platform}

维护您的域和IP地址信誉至关重要。 以下是建立新平台的一些建议。

开始在新平台上发送电子邮件是一个敏感步骤，因为该平台没有任何使用历史记录和信誉（当发送的IP从未用于此目的时）。 ISP自然会怀疑从未用来发送电子邮件的IP地址，并突然开始发送大量电子邮件流量。 实际上，垃圾邮件发送者通常会使用“未知”IP地址(从未添加到程序的地阻止列表址)发送尽可能多的邮件，然后再进行检测。

在生产阶段的开始，您无法期望在输出方面达到操作速度。 此外，您不应尝试以此速率发送消息，因为这可能会导致ISP阻止发送地址，并严重危害开始的其余阶段。

首次使用列表地址时，通常会启动平台，而该地址可能未完全限定。 如果发送到无效地址或蜜罐地址，这会降低平台的声誉。
* 如果列表的地址无效，则在首次发送前将其导入隔离表(**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Quarantines]** > **[!UICONTROL Addresses]**)符合您的最大利益。 有关更多信息，请参阅[此章节](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform)。
* 如果您仍希望重新指定无效地址，则最好在建立平台信誉并逐位地执行此操作，以便随着时间的推移“稀释”使用不良地址。

总结在启动时应遵循的原则：
* **配置专用子** 域，使用特定于从活动发送的电子邮件活动的Adobe。
* **将无效／非活动地址导入隔离表** （如果您有此信息）。
* **限制投放** 吞吐量(技术设置：限制mtachild的数量)。
* **逐渐增加发送的卷**:不要从整个开始中目标整个列表库，而是每次发送时都额外添加的一小部分。这样，您就可以在每一步增加卷，同时降低无效地址的总体速率。
* **定期发送消息**:从某种程度上讲，最好定期发送小照片，而不是偶尔发大活动。
* **密切关注投放报告**:高错误指示器可能意味着技术设置配置不当。
