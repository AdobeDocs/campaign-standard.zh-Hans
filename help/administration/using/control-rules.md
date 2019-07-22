---
title: 控制规则
seo-title: 控制规则
description: 控制规则
seo-description: 了解如何通过控制规则加强消息的质量检查。
page-status-flag: 从未激活
uuid: 33a1c90c-534e-4fe1-982c-f4 e1858 d4 d2 d
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: 使用字型规则
discoiquuid: 305cadde-6424-4c6f-b11 b-1e8 bdwug6 ef1
internal: n n
snippet: y
translation-type: tm+mt
source-git-commit: 5e5532c0769fe33016eaee994bdaae9c70a7eaa5

---


# Control rules{#control-rules}

控制规则允许用户在发送消息之前检查消息的有效性和质量，如字符显示、SMS消息大小、地址格式等。

Adobe Campaign中提供的一系列默认规则可确保标准控制：

* **[!UICONTROL Check subject]** (电子邮件)：检查主题和发送者地址是否包含可能在某些邮件传输代理上造成问题的特殊字符，并检查邮件主题是否已完成。
* **[!UICONTROL Check URL labels]** (电子邮件)：检查每个跟踪URL是否有一个标签。
* **[!UICONTROL Check URLs]** (电子邮件)：检查跟踪URL(是否存在“&amp;”字符)。
* **[!UICONTROL Check proof size]** (所有渠道)：如果证据目标人群超过100个收件人，则生成错误消息。
* **检查取消订阅链接** (电子邮件)：检查每个内容中是否存在至少一个取消订阅(选择退出) URL(HTML和文本)。
* **[!UICONTROL Check delivery size]** (所有渠道)：检查消息的大小。
* **[!UICONTROL Check social network sharing link]** (电子邮件)：在内容中包括社交网络共享链接(VirallLinks)时检查镜像页面是否存在链接。
* **[!UICONTROL A/B Test]**：通过A/B测试提取测试人群。

您可以选择将规则从交付周期的某个阶段应用到的时刻。Select the value to apply in the drop-down list from the **[!UICONTROL Phase]** field of the typology rule.

![](assets/typology_phase.png)

可能的值有：

* **在定位之初**

   控制规则可在此阶段应用，以便在出错时不执行个性化步骤。

* **定位后**

   如果您需要了解目标的音量以应用控制规则，请选择此阶段。

   For example, the **Check proof size** control rule applies after the targeting stage: this rule prevents the preparation of message personalization if there are too many proof recipients.

* **在个性化之初**

   如果检查批准消息个性化，必须选择此阶段。在分析阶段执行消息个性化。

* **在分析结束时**

   当检查需要消息个性化完成时，请选择此阶段。

>[!NOTE]
>
>由于安全原因，无法修改控制规则的内容。**[!UICONTROL Code]** 字段为只读字段。
